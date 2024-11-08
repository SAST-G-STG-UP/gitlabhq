---
stage: Create
group: Editor Extensions
info: To determine the technical writer assigned to the Stage/Group associated with this page, see https://handbook.gitlab.com/handbook/product/ux/technical-writing/#assignments
description: "Use the GitLab Workflow extension for VS Code to handle common GitLab tasks directly in VS Code."
---

# GitLab Workflow extension for VS Code

The [GitLab Workflow extension](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow)
for Visual Studio Code integrates GitLab Duo and other GitLab features directly into your IDE.

The GitLab Workflow extension streamlines your VS Code workflow with AI-assisted features:

- **GitLab Duo Chat**: Interact with an AI assistant directly in VS Code. See
  [how to set up GitLab Duo Chat](../../user/gitlab_duo_chat/index.md#use-gitlab-duo-chat-in-vs-code).
- [**GitLab Duo Code Suggestions**](#code-suggestions-features): Suggest completions to your current line of code,
  or write natural-language code comments to get more substantive suggestions.

## Code Suggestions features

GitLab Duo Code Suggestions provides AI-powered suggestions as you type in VS Code, helping you write code more efficiently.
To interact with a [suggestion](../../user/project/repository/code_suggestions/index.md) on the current line:

- To accept the entire suggestion, press <kbd>Tab</kbd>.
- To accept the suggestion word-by-word, press <kbd>Command</kbd> + <kbd>→</kbd> (right arrow).
- To accept an entire line, right-click and select **Accept Line**.

GitLab Duo can also generate code based on comments in the file you're editing in VS Code. When you write comments in a
[supported file type](https://gitlab.com/gitlab-org/editor-extensions/gitlab-lsp/-/tree/main/vendor/grammars?ref_type=heads),
use natural language to describe what you want the code to do. Press <kbd>Enter</kbd> to see suggestions from
GitLab Duo inline in your current file.

To learn more, see the [documentation for Code Suggestions](../../user/project/repository/code_suggestions/index.md).

### Configure more languages for Code Suggestions

To add more languages to Code Suggestions:

1. Find your desired language in the list of
   [language identifiers](https://code.visualstudio.com/docs/languages/identifiers#_known-language-identifiers)
   for VS Code. You need the **Identifier** for a later step.
1. In VS Code, open the extension settings for **GitLab Workflow**:
   1. On the top bar, go to **Code > Settings > Extensions**.
   1. Search for **GitLab Workflow** in the list, then select **Manage** (**{settings}**) **> Extension Settings**.
   1. In your **User** settings, find
      **GitLab › Duo Code Suggestions: Additional Languages** and select **Add Item**.
1. In **Item**, add the language identifier, and select **OK**.

## Set up the GitLab Workflow extension

This extension requires you to create a GitLab personal access token, and assign it to the extension:

1. [Install the extension](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow) from the Visual Studio Marketplace and enable it. If you use an unofficial version of VS Code, install the extension from the [Open VSX Registry](https://open-vsx.org/extension/GitLab/gitlab-workflow).
1. To sign in to your GitLab instance, run the command **GitLab: Authenticate** in VS Code.
   1. Open the Command Palette:
      - For macOS, press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
      - For Windows or Linux, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
   1. In the Command Palette, search for **GitLab: Authenticate** and press <kbd>Enter</kbd>.
   1. Select your GitLab instance URL from the offered options, or enter one manually.
      - When manually adding an instance to **URL to GitLab instance**, paste the full URL to your
        GitLab instance, including the `http://` or `https://`. Press <kbd>Enter</kbd> to confirm.
   1. For `GitLab.com`, you can use the OAuth authentication method.
   1. If you don't use OAuth, use a personal access token to sign in.
      - If you have an existing personal access token with `api` scope, select **Enter an existing token** to enter it.
      - If you don't, select **Create a token first**, and the extension opens the token settings page for you.
        If this method fails, follow the instructions to [create a personal access token](../../user/profile/personal_access_tokens.md#create-a-personal-access-token).
   1. Copy the token. _For security reasons, this value is never displayed again, so you must copy this value now._
   1. Paste in your GitLab personal access token and press <kbd>Enter</kbd>. The token is not displayed, nor is it accessible to others.

The extension matches your Git repository remote URL with the GitLab instance URL you specified
for your token. If you have multiple accounts or projects, you can choose the one you want to use.
For more details, see [Account management](https://gitlab.com/gitlab-org/gitlab-vscode-extension/#account-management).

The extension shows information in the VS Code status bar if both:

- Your project has a pipeline for the last commit.
- Your current branch is associated with a merge request.

## Configure extension settings

After you install GitLab Workflow, go to **Settings > Extensions > GitLab Workflow** in VS Code to configure its settings:

- [GitLab Duo Chat](../../user/gitlab_duo_chat/index.md#use-gitlab-duo-chat-in-vs-code).
- [Features to display or hide](https://gitlab.com/gitlab-org/gitlab-vscode-extension#extension-settings).
- [Self-signed certificate](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#self-signed-certificates) information.
- [Code Suggestions](../../user/project/repository/code_suggestions/index.md).

### Customize keyboard shortcuts

You can assign different keyboard shortcuts for **Accept Inline Suggestion**, **Accept Next Word Of Inline Suggestion**,
or **Accept Next Line Of Inline Suggestion**:

1. In VS Code, run the `Preferences: Open Keyboard Shortcuts` command.
1. Find the shortcut you want to edit, and select **Change keybinding** (**{pencil}**).
1. Assign your preferred shortcuts to **Accept Inline Suggestion**, **Accept Next Word Of Inline Suggestion**,
   or **Accept Next Line Of Inline Suggestion**.
1. Press <kbd>Enter</kbd> to save your changes.

## Integrate with GitLab

This extension brings the GitLab features you use every day directly into your VS Code environment:

- [View issues](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#browse-issues-review-mrs) and merge requests.
- Run [common commands](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#commands)
  from the Visual Studio Code [Command Palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).
- Create and [review](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#merge-request-reviews)
  merge requests.
- [Validate your GitLab CI/CD configuration](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#validate-gitlab-cicd-configuration).
- View [pipeline status](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#information-about-your-branch-pipelines-mr-closing-issue) and
  [job outputs](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#view-the-job-output).
- [Create](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#create-snippet) and manage snippets.
- [Browse repositories](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow#browse-a-repository-without-cloning)
  without cloning them.
- [View security findings](https://marketplace.visualstudio.com/items?itemName=gitlab.gitlab-workflow#security-findings).

For detailed information on these features, refer to the [GitLab Workflow extension documentation](https://gitlab.com/gitlab-org/gitlab-vscode-extension/-/blob/main/README.md).

## Create a snippet

Create a [snippet](../../user/snippets.md) to store and share bits of code and text with other users.
Snippets can be a selection or an entire file.

To create a snippet in VS Code:

1. Choose the content for your snippet:
   - For a **Snippet from file**, open the file.
   - For a **Snippet from selection**, open the file and select the lines you want to include.
1. Open the Command Palette:
   - For macOS, press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
   - For Windows or Linux, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. In the Command Palette, run the command `GitLab: Create Snippet`.
1. Select the snippet's privacy level:
   - **Private** snippets are visible only to project members.
   - **Public** snippets are visible to everyone.
1. Select the snippet's scope:
   - **Snippet from file** uses the entire contents of the active file.
   - **Snippet from selection** uses the lines you selected in the active file.

GitLab opens the new snippet's page in a new browser tab.

### Create a patch file

When you review a merge request, create a snippet patch when you want to suggest multi-file changes.

1. On your local machine, check out the branch you want to propose changes to.
1. In VS Code, edit all files you want to change. Do not commit your changes.
1. Open the Command Palette:
   - For macOS, press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
   - For Windows or Linux, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. In the Command Palette, enter `GitLab: Create snippet patch`, and select it. This command runs a
   `git diff` command and creates a GitLab snippet in your project.
1. Enter a **Patch name** and press <kbd>Enter</kbd>. GitLab uses this name as the
   snippet title, and converts it into a filename appended with `.patch`.
1. Select the snippet's privacy level:
   - **Private** snippets are visible only to project members.
   - **Public** snippets are visible to everyone.

VS Code opens the snippet patch in a new browser tab. The snippet patch's
description contains instructions on how to apply the patch.

### Insert a snippet

To insert an existing single-file or [multi-file](../../user/snippets.md#add-or-remove-multiple-files) snippet from a project you are a member of:

1. Place your cursor where you want to insert the snippet.
1. Open the Command Palette:
   - For macOS, press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
   - For Windows or Linux, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. Type `GitLab: Insert Snippet` and select it.
1. Select the project containing your snippet.
1. Select the snippet to apply.
1. For a multi-file snippet, select the file to apply.

## Search issues and merge requests

To search your project's issues and merge requests directly from VS Code, use filtered search or
[Advanced Search](../../integration/advanced_search/elasticsearch.md). With filtered search,
you use predefined tokens to refine your search results.
Advanced Search provides faster, more efficient search across the entire GitLab instance.

Prerequisites:

- You're a member of a GitLab project.
- You've installed the [GitLab Workflow extension](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow).
- You've signed in to your GitLab instance, as described in [Setup](https://gitlab.com/gitlab-org/gitlab-vscode-extension/-/tree/main/#setup).

To search the titles and description fields in your project:

1. In VS Code, open the Command Palette:
   - For macOS, press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
   - For Windows or Linux, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. Select your desired search type: `GitLab: Search project merge requests` or `GitLab: Search project issues`.
1. Enter your text, using [filter tokens](#filter-searches-with-tokens) as needed.
1. To confirm your search text, press <kbd>Enter</kbd>. To cancel, press <kbd>Escape</kbd>.

GitLab opens the results in a browser tab.

### Filter searches with tokens

Searches in large projects return better results when you add filters. The extension supports these tokens
for filtering merge requests and issues:

| Token     | Example                                                            | Description |
|-----------|--------------------------------------------------------------------|-------------|
| assignee  | `assignee: timzallmann`                                            | Username of the assignee, without `@`. |
| author    | `author: fatihacet`                                                | Username of the author, without `@`. |
| label     | `label: frontend` or `label:frontend label: Discussion`            | A single label. Usable more than once, and can be used in the same query as `labels`. |
| labels    | `labels: frontend, Discussion, performance`                        | Multiple labels in a comma-separated list. Can be used in the same query as `label`. |
| milestone | `milestone: 18.1`                                                  | Milestone title without `%`. |
| scope     | `scope: created-by-me` or `scope: assigned-to-me` or `scope: all`. | Issues and merge requests matching the given scope. Values: `created-by-me` (default), `assigned-to-me` or `all`. |
| title     | `title: discussions refactor`                                             | Issues and merge requests with title or description matching these words. Don't add quotation marks around phrases. |

Token syntax and guidelines:

- Each token name requires a colon (`:`) after it, like `label:`.
  - A leading space for the colon (`label :`) is invalid and returns a parse error.
  - A space after the token name is optional. Both `label: frontend` and `label:frontend` are valid.
- You can use the `label` and `labels` tokens multiple times and together. These queries return the same results:
  - `labels: frontend discussion label: performance`
  - `label: frontend label: discussion label: performance`
  - `labels: frontend discussion performance` (the resulting, combined query)

You can combine multiple tokens in a single search query. For example:

```plaintext
title: new merge request widget author: fatihacet assignee: jschatz1 labels: frontend, performance milestone: 17.5
```

This search query looks for:

- Title: `new merge request widget`
- Author: `fatihacet`
- Assignee: `jschatz1`
- Labels: `frontend` and `performance`
- Milestone: `17.5`

## Related topics

- [Download the GitLab Workflow extension](https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow)
- Extension [source code](https://gitlab.com/gitlab-org/gitlab-vscode-extension/)
- [GitLab Duo documentation](../../user/project/repository/code_suggestions/index.md)
