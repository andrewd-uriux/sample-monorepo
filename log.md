npx lerna clean
git add .
git commit -m 'initial commit'
git status
# removed workspace configuration from package.jsona nd created a pnpm-workspace.yaml file to be used instead
pnpm install
# got expected error error when i did this: GET https://registry.npmjs.org/@sample%2Fapp: Not Found - 404
# node modules were built


do a search and replace for
git@github.com:wixplosives/sample-monorepo.git
and
git@github.com:andrewd-uriux/sample-monorepo.git
