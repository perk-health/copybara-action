| Input              | Required | Default                             | Description                                                                                                                                                  |
| ------------------ | -------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ssh_key            | yes      |                                     | SSH public key.                                                                                                                                              |
| access_token       |          |                                     | Personal access token with `repo` permissions. Always required on *destination* and required on *SoT* only if the variable `sot_branch` below is left empty. |
| sot_repo           |          |                                     | Source repository (Source of Truth).                                                                                                                         |
| sot_branch         |          |                                     | SoT branch. Leave empty to use your repository's default branch.                                                                                             |
| destination_repo   |          |                                     | Destination repository.                                                                                                                                      |
| destination_branch |          |                                     | Destination branch. Leave empty to use the same as your SoT's branch name.                                                                                   |
| make_root_path     |          |                                     | Use a sub-path of the source repo as root for the destination repo.                                                                                          |
| include_files_sot  |          | **                                  | Files to include when pushing from SoT => Destination (comma separated globs).                                                                               |
| exclude_files_sot  |          |                                     | Files to exclude when pushing from SoT => Destination (comma separated globs).                                                                               |
| include_files_dest |          | **                                  | Files to include when pulling from Destination => SoT (comma separated globs).                                                                               |
| exclude_files_dest |          |                                     | Files to exclude when pulling from Destination => SoT (comma separated globs).                                                                               |
| committer          |          | Github Actions <actions@github.com> | Who will commit changes.                                                                                                                                     |
| default_author     |          | Github Actions <actions@github.com> | Default author if the original author can't be used for some reason.                                                                                         |
| custom_config      |          |                                     | Copybara configuration file to use.                                                                                                                          |
| workflow           |          |                                     | Workflow to execute. Leave empty to auto-detect (init / push / pr).                                                                                          |
| copybara_options   |          |                                     | Use this, if you want to manually specify some command line options (space-separated).                                                                       |
| ssh_known_hosts    |          |                                     | SSH known hosts file contents, for authenticating with Copybara.                                                                                             |
| copybara_image     |          | olivr/copybara                      | Copybara Docker image to run.                                                                                                                                |
| copybara_image_tag |          | latest                              | Copybara Docker image tag to use.                                                                                                                            |
| pr_number          |          |                                     | If you manually specified the 'pr' workflow, you will need to specify the PR number as well.                                                                 |
| create_repo        |          | yes                                 | If the destination repo doesn't exist, it will be created (subject to enough permissions attached to the access token).                                      |