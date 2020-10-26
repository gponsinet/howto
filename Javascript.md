# How to Javascript

## Install

First, install [volta](https://volta.sh):
```bash
curl https://get.volta.sh | bash
```

Volta permit you to manage your nodejs environment, for more information see [here](https://docs.volta.sh/guide/#why-volta).

## Setup project

```bash
mkdir $YOUR_PROJECT_NAME
cd $YOUR_PROJECT
volta install node@15
volta pin node@15
npm init -y
echo 'node_modules' >> .gitignore
```

## Transpiling

```bash
cd $YOUR_PROJECT
npm install --save-dev @babel/cli @babel/node babel-preset-expo

echo 'module.exports = (api) => {
	api.cache(true)

	return {
		presets: ['babel-preset-expo'],
	}
}' > babel.config.js
```

## Linting

```bash
cd $YOUR_PROJECT
volta install eslint-cli
npm install --save-dev eslint_d @babel/eslint-parser @react-native-community/eslint-config
ln -sf eslint_d node_modules/.bin/eslint
git add -f node_modules/.bin/eslint

echo 'const path = require('path')
module.exports = {
	root: true,
	parser: '@babel/eslint-parser',

	parserOptions: {
		sourceType: 'module',

		babelOptions: {
			configFile: path.join(__dirname, 'babel.config.js'),
		},
	},

	extends: [
		'@react-native-community',
		'prettier',
		'prettier/@typescript-eslint',
		'prettier/babel',
		'prettier/react',
	],
}' > .eslintrc.js
```
