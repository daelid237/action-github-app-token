# action-github-app-token

This uses GitHub Apps to fetch an auth token for an App installation

## Development

Install the dependencies
```bash
$ yarn
```

Build the typescript and package it for distribution
```bash
$ yarn build
```

## Usage

The action will provide a `token` output.

```
  - name: my-app-install token
    id: my-app
    uses: 'getsentry/action-github-app-token'
    with:
      private_key: ${{ secrets.APP_PRIVATE_KEY }}

  - name: Checkout private repo
    uses: actions/checkout@v2
    with:
      repository: getsentry/my-private-repo
      token: ${{ steps.my-app.output.token }}
```
