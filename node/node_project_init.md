## Create a node app

#### Initialize an empty ts project

- npm init -y
- npx tsc --init

#### change the rootDir and outDir in tsconfig.json

- "rootDir": "./src",
- "outDir": "./dist"

#### common packages

- npm i nodemon express dotenv rimraf cors
- npm i -D @types/express @types/cors

#### add scripts to package.json

"scripts": {
"build": "rimraf dist && npx tsc",
"prestart": "npm run build",
"start": "node dist/index.js",
"predev": "npm run build",
"dev": "tsc -w & nodemon dist/index.js"
}

#### make a .env and .gitignore file

#### Initialize prisma and add dependencies

- npm i -D prisma
- npx prisma init
