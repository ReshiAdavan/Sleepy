# Sleepy

Sleepy is a GitHub Action tool that leverages OpenAI's GPT-4 API to provide intelligent feedback and suggestions on
your pull requests. It helps improve code quality and saves developers time by automating PR
review processes.

## Inspiration

Reviews are one of the biggest reasons why code fails or takes too long to reach production. I notice a lot of tech leads and senior engineers who spend a lot of time reviewing PRs because they have to, and it takes too much time away from other important endeavours. As of the recent breakthrough of AI, I believe it would be more efficient to leverage AI in code reviews, especially if it has been trained over billions of lines of code and if it can generate great reviews in seconds.  

## How It Works

Sleepy retrieves pull request diffs, filters out excluded files, and sends code chunks to
the OpenAI API. It then generates review comments based on the AI's response and adds them to the pull request.

## Use It Yourself

1. Sign up for an API key at [OpenAI](https://beta.openai.com/signup) if you don't have one.

2. Add the OpenAI API key as a GitHub Secret in your repository with name `OPENAI_API_KEY`. 
More info on GitHub Secrets [here](https://docs.github.com/en/actions/reference/encrypted-secrets).

3. Create a `.github/workflows/main.yml` file in the repository you want this tool to function in with the following content:

```yaml
name: Sleepy the Code Reviewer
on:
  pull_request:
    types:
      - opened
      - synchronize
permissions: write-all
jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v3

      - name: Sleepy the Code Reviewer
        uses: ReshiAdavan/Sleepy@master
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
          OPENAI_API_MODEL: "gpt-4" # Optional: defaults to "gpt-4"
          exclude: "**/*.json, **/*.md" # Optional: exclude patterns separated by commas
```

## Examples

To see live examples of the code review tool in action, refer to the  [Compilation of Examples](https://github.com/ReshiAdavan/Sleepy/blob/master/src/README.md)
