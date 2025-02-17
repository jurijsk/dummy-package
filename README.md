# dummy
This repo will contain nothing expect readme and some other BS just to text checkout with PET. Novel idea huh. 

## How to GitHub Packages publishing works

To publish to GitHub Packages I've used [GitHub template](https://github.com/jurijsk/dummy/actions/new?category=continuous-integration&query=Publish+Node.js+Package+to+GitHub+Packages) with a couple of change, which include:
 * Changed default befaviour to only publish on `relese: types: [created]` (see lines:6-8) to publich on every commit.
 * Added git config calls to set `user.name` and `user.email` to avoid errors from git
 * Added `- run: npm version patch` (line:36) to automatically increment patch number (x.x.++)
 * Removed `- run: npm test` (around line ~20) cos i do not have any tests.

Notes:
 * No tokens stored anywhere in the repo, the workflow relies on `GITHUB_TOKEN` with is autogenerated and it has access to the repo and can do anything it needs to publish.
 * Note that `.npmrc` is not present as all the details needed for publish on commit are stated in `yml` itself.
 * No `.npmrc` is required because all the information need is in the `yml` file, but
 * Make sure to give proper permission to `GITHUB_TOKEN` including write access to the current repo in package setting and write access to all scopes in repo's `Settings->Actions` 


v1.0.1
	- nothing new just a test for Github Action to publish new version of the package

v1.0.2 
	- Adding package.lock with no packages to make `npm ci` shut up
	- removing unscoped `repository` from `.npmrc` to make instalations from public repost possible
	- send it
v1.0.3
	- Getting rid of `      - run: npm test` is the GitHub Actions workflow
v1.0.4
	- trying to deal with the vesion number
v1.0.5
	- trying to deal with the vesion number #2
v1.0.6
	- setting user name and email
v1.0.7
	- setting user name and email #2
v1.0.8
	- fixing `error: unable to sign the tag`
v1.1.0
	- changing vesion to 1.1
v1.1.2
	- added some notes on how the package is published
v1.1.3
	- added some notes on `.npmrc`
v1.1.4
	- fixing the publishing problem
v1.1.5
	- removing `.npmrc`