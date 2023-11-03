# Sleepy

Sleepy is a GitHub Action tool that leverages OpenAI's GPT-4 API to provide intelligent feedback and suggestions on
your pull requests. It helps improve code quality and saves developers time by automating PR
review processes.

## Inspiration

Reviews are one of the biggest reasons why code dont get pushed/take too long to get pushed. Instead of spending my time reviewing PRs, I would rather leverage AI especially if it can be trained to surf XXM lines of code in minutes and create the best possible review.  

## How It Works

Sleepy retrieves pull request diff, filters out excluded files, and sends code chunks to
the OpenAI API. It then generates review comments based on the AI's response and adds them to the pull request.