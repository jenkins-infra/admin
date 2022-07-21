# GitHub Safe-Settings (`admin` special repository)

[`Safe-settings`](https://github.com/github/safe-settings/)– an app to manage policy-as-code and apply repository settings to repositories across an organization.

1. In `safe-settings` all the settings are stored centrally in an `admin` repo within the organization. This is important. Unlike [Settings Probot](https://github.com/probot/settings), the settings files cannot be in individual repositories.
1. There are 3 levels at which the settings could be managed:
   1. Org-level settings are defined in `.github/settings.yml` 
   1. `Suborg` level settings. A `suborg` is an arbitrary collection of repos belonging to projects, business units, or teams. The `suborg`settings reside in a yaml file for each `suborg` in the `.github/suborgs`folder.
   1. `Repo` level settings. They reside in a repo specific yaml in `.github/repos`folder
1. It is recommended to break the settings into org-level, suborg-level, and repo-level units. This will allow different teams to be define and manage policies for their specific projects or business units.With `CODEOWNERS`, this will allow different people to be responsible for approving changes in different projects.

**Note:** The settings file must have a `.yml`extension only. `.yaml` extension is ignored, for now.
