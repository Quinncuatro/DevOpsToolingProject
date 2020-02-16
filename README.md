# DevOps Tooling Project

## Abstract

I want to consolidate the tools we're building under a common set of languages (JavaScript/Python) and one deployment strategy (AWS Lambda). This well help us accomplish a few things:

1. Since we're moving to AWS anyway, this is a good way for us to get our feet wet. We can then empower Clarity's developers to build and deploy their own tools.
2. We get to move away from Jenkins; saving time, effort, and frustration in getting current and experimental tools up and running.
3. Standardizing the DevOps toolkit to a common coding and deployment practice amongst all of us will empower our team to move faster and cover each others' gaps.

## Building Blocks

### Infrastructure
- API Front
- AWS Lambda

### Tools
- Gobstopper
- PhiByeBye
- ScriptMover

### Wishlist
- Atlassian API
- CI/CD
- Logging With CloudWatch
- Testing

## Gameplan

### Gobstopper
- Add more functionality to parser
- -> Deploy to Lambda

### PhiByeBye
- Punch up Tim's new "all or nothing" script
- -> Add some comments, logging, safety backups
- -> Convert to Node/Python
- -> Deploy to Lambda

### ScriptMover
- Convert to Node/Python
- -> Plug in Atlassian API: Build Audit -> Jira Tickets -> ScriptMover
- -> Demploy to Lambda

### Atlassian API
- Use build audit to get tickets based on date
- -> Per ticket, see if there are cron, shell, SQL included
- -> Grab inflight dir path per ticket
- -> Run Git scripts to move files
- -> Plug values into Jira tickets
- -> Plug values into build audit page

### Toolchain API
- Build a tool similar to Evan's Kraken
- One CLI tool on all of our machines to trigger cloud native Lambda functions
- Pipe output to both S3 and our local terminals

## Various Benefits

### From Moving to AWS
- Easy way to move resource-hogging scripts off our local machines.
- Way less setup per job (no app server, Docker containers, or Jenkins) - promotes experimentation of automation tasks.
- Using a framework like Serverless (for Node AND Python) will help us remain cloud agnostic.
- Eating our own dogfood will allow us to help the devs build and roll their own tools.
- Only one platform to set up Datadog against - rather than having Tim keep track of various boxes.

### From Toolchain Standardization
- Built in safety features if they're used across the whole suite of tools.
- Centralized environment variables for creds to other boxes.
- Settle on two languages: JavaScript and Python.
- Standardize how to handle things like comments, flags, and logging.
- Standardize use of graceful exits - fail fast and LOUD to whole group (not just person running the job).
- Once adopted, our department will continue to speed up, since we'll all be rallied around a common set of development tools.
