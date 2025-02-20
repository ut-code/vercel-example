This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

* gitリポジトリをつくります
```sh
npx create-next-app@latest
```
* GitHubにpushします
* Vercelにプロジェクトを作ります。ただし、VercelのUIからではなく次のようにコマンドからやります。
```sh
npx vercel deploy
```
```
Vercel CLI 41.1.4
? Set up and deploy “~/projects/vercel-example”? yes
? Which scope should contain your project? natrium144's projects
? Link to existing project? no
? What’s your project’s name? vercel-example
? In which directory is your code located? ./
Local settings detected in vercel.json:
Auto-detected Project Settings (Next.js):
- Build Command: next build
- Development Command: next dev --port $PORT
- Install Command: `yarn install`, `pnpm install`, `npm install`, or `bun install`
- Output Directory: Next.js default
? Want to modify these settings? no
🔗  Linked to natrium144s-projects/vercel-example (created .vercel)
```
* Vercel の Account Settings → Tokens へ行き、Tokenを作成します
* GitHubでリポジトリの Settings → Secrets and variables → Actions へ行き、 Repository Secrets に以下を追加しましょう
    * `VERCEL_TOKEN`: 先ほど作成したToken
    * `VERCEL_ORG_ID`: .vercel/project.json 内にある `orgId`
    * `VERCEL_PROJECT_ID`: .vercel/project.json 内にある `projectId`
* [GitHub ActionのWorkflowファイル](.github/workflows)を作成し、pushします。([これ](https://vercel.com/guides/how-can-i-use-github-actions-with-vercel)のコピペですが)
* main以外のブランチに変更がpushされるとpreviewとしてデプロイされ、mainに変更がpushされるとproductionとしてデプロイされます
