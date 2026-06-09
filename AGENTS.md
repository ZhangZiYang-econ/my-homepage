# Project Operating Instructions

## User Context

- The user is an economics researcher specializing in macroeconomics.
- Their research interests include structural transformation, automation and artificial intelligence, and income distribution.
- They are currently pursuing a PhD in economics at the School of Economics, Renmin University of China.

## Assistant Role

- The assistant's role in this project is to help the user update and maintain their personal academic homepage at appropriate times.

## Safety Rules

- Only delete files or directories in bulk when the user explicitly asks for that exact action.
- Bulk deletion of files or directories is otherwise prohibited.
- Preserve user changes in the working tree unless the user explicitly asks to revert or remove them.

## Default Website Update Workflow

When the user asks to update website content, run the local update workflow:

1. Update the relevant local source files in this repository.
2. Rebuild or verify the site using the repository's existing tooling.
3. Provide the user with ready-to-run commands for committing, pushing to GitHub, and deploying to Netlify.
4. Report the expected public website URL or deploy preview URL when it can be inferred from the repository configuration.

The assistant has previously been unable to automatically push to GitHub or deploy to Netlify in this sandbox. Do not repeatedly retry those remote publishing steps unless the user explicitly asks for an automatic attempt. Instead, provide the exact final-step commands for the user to run.

If automatic commit, push, or deployment cannot be completed by the assistant, provide the user with a ready-to-run script, program, or exact commands that can complete the blocked step.

When providing final-step publishing commands for the user to run on Windows, use this concise command block by default:

```cmd
cd /d F:\My_academic_site
git push origin main
npx netlify deploy --prod --dir=_site
```

If the changes have not yet been committed locally, also provide any needed `git add` and `git commit` commands before `git push origin main`.

## Publishing Trigger Phrases

If the user says any of the following phrases after requesting content changes, treat it as a request to prepare the final GitHub and Netlify publishing commands:

- "发布"
- "推送"
- "部署"
- "上线"
- "更新网站"
- "更新主页"
- "同步到GitHub"
- "部署到Netlify"
- "给我最后一步命令"
