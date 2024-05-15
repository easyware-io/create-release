# easyware-io/create-release@v1

![CI](https://github.com/easyware-io/create-release/actions/workflows/build.yml/badge.svg)

An Action to create releases via the GitHub Release API

## Usage

### Basic usage

```yaml
- name: Create release
  uses: easyware-io/create-release@v1
  with:
    tag: v1.0.0
    token: ${{ secrets.GITHUB_TOKEN }}
    releaseTitle: v1.0.0
    releaseBody: <optional>
    owner: <optional>
    repo: <optional>
```

The action results an output called `data` that has this information:

```json
{
  "url": "https://github.com/api/v3/repos/easyware-io/create-release/releases/53665",
  "assets_url": "https://github.com/api/v3/repos/easyware-io/create-release/releases/53665/assets",
  "upload_url": "https://github.com/api/uploads/repos/easyware-io/create-release/releases/53665/assets{?name,label}",
  "html_url": "https://github.com/easyware-io/create-release/releases/tag/v1.0.0",
  "id": 53665,
  "author": {
    "login": "username",
    "id": 1595,
    "node_id": "MDQ6VXNlcjE1OTU=",
    "avatar_url": "https://avatars.github.com/u/1595?",
    "gravatar_id": "",
    "url": "https://github.com/api/v3/users/username",
    "html_url": "https://github.com/username",
    "followers_url": "https://github.com/api/v3/users/username/followers",
    "following_url": "https://github.com/api/v3/users/username/following{/other_user}",
    "gists_url": "https://github.com/api/v3/users/username/gists{/gist_id}",
    "starred_url": "https://github.com/api/v3/users/username/starred{/owner}{/repo}",
    "subscriptions_url": "https://github.com/api/v3/users/username/subscriptions",
    "organizations_url": "https://github.com/api/v3/users/username/orgs",
    "repos_url": "https://github.com/api/v3/users/username/repos",
    "events_url": "https://github.com/api/v3/users/username/events{/privacy}",
    "received_events_url": "https://github.com/api/v3/users/username/received_events",
    "type": "User",
    "site_admin": false
  },
  "node_id": "MDc6UmVsZWFzZTUzNjY1",
  "tag_name": "v1.0.0",
  "target_commitish": "branch_name",
  "name": "v1.0.0",
  "draft": false,
  "prerelease": false,
  "created_at": "2024-05-14T10:08:54Z",
  "published_at": "2024-05-14T15:48:49Z",
  "assets": [],
  "tarball_url": "https://github.com/api/v3/repos/easyware-io/create-release/tarball/v1.0.0",
  "zipball_url": "https://github.com/api/v3/repos/easyware-io/create-release/zipball/v1.0.0",
  "body": ""
}
```

If an error occurs, `data` will return as `null`.
