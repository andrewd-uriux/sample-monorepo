npx lerna clean
git add .
git commit -m 'initial commit'
git status
# removed workspace configuration from package.jsona nd created a pnpm-workspace.yaml file to be used instead

in lerna.json, edit to remove the useWorkspaces and change client.
{
  "npmClient": "pnpm",
  "version": "independent"
}



pnpm install
# got expected error error when i did this: GET https://registry.npmjs.org/@andrewd-uriux%2Fapp: Not Found - 404
# node modules were built


do a search and replace for
git@github.com:wixplosives/sample-monorepo.git
and
git@github.com:andrewd-uriux/sample-monorepo.git


npm login --registry=https://npm.pkg.github.com --scope=@uri-cloudops

package version not found:
add version to root package.json


pnpm publish --no-git-checks --registry=https://npm.pkg.github.com/   # works from root of directory but gave error : remove private from package.json because i'm publishing to public repo i guess

remove private


pnpm run build

now fix any broken imports by replacing the @andrewd-uriux with local file paths like ../../components/src/main.js

now that pnpm run build is working, try publishing

go into each  package and
run pnpm install

if the package fails, then do the next one. and keep iterating through to the next one . eventually one will pass and then the other ones will pass


cd packages/components
pnpm  install
pnpm publish --no-git-checks --registry=https://npm.pkg.github.com/

cd ../server
pnpm  install
pnpm publish --no-git-checks --registry=https://npm.pkg.github.com/


cd ../app
pnpm  install
pnpm publish --no-git-checks --registry=https://npm.pkg.github.com/





Errors:
npm error code EPRIVATE
npm error This package has been marked as private
npm error Remove the 'private' field from the package.json to publish it.
npm error A complete log of this run can be found in: /Users/andrewd/.npm/_logs/2025-03-09T02_36_44_555Z-debug-0.log

just remove the
private:true from package.json

