# Sleepy

Sleepy is a GitHub Action tool that leverages OpenAI's GPT-4 API to provide intelligent feedback and suggestions on
your pull requests. It helps improve code quality and saves developers time by automating PR
review processes.

## Inspiration

Unfinished

## How It Works

Sleepy retrieves pull request diff, filters out excluded files, and sends code chunks to
the OpenAI API. It then generates review comments based on the AI's response and adds them to the pull request.