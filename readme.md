## How to configure eslint

1. Install eslint:
```
npm init @eslint/config
```

2. Configurate eslint with your preferences:

![image](https://github.com/jarrisondev/how-to-configure-eslint-and-prettier/assets/62910118/573ee570-4cc6-4d01-95a6-836342a0c23f)

3. Install with a node package manager the next dependencies:
```

  npm install -D eslint-config-prettier eslint-plugin-prettier

  or

  yarn add -D eslint-config-prettier eslint-plugin-prettier

```
   
6. In the **extend** property of your **.eslintrc.cjs |  .eslintrc.js |  .eslintrc.json** file, add the **plugin:prettier/recommended**:
```
extends: [..., 'plugin:prettier/recommended'],
```
7. In the **plugins** property of your **.eslintrc.cjs |  .eslintrc.js |  .eslintrc.json** file, add the **prettier** plugin:
```
plugins: [..., 'prettier'],
```
8. In the **rules** property of your **.eslintrc.cjs |  .eslintrc.js |  .eslintrc.json** file, add the following rule:
```
rules:{
  ...,
  'prettier/prettier': 0,
  ...,
}
```
## How to configure prettier
I use prettier with a plugin with 
1. Create a file with the name **prettier.config.cjs** and add the next

```
/** @typedef  {import("@ianvs/prettier-plugin-sort-imports").PluginConfig} SortImportsConfig */
/** @typedef  {import("prettier").Config} PrettierConfig */

/** @type { PrettierConfig | SortImportsConfig | TailwindConfig } */
const config = {
	semi: false,
	singleQuote: true,
	jsxSingleQuote: true,
	printWidth: 120,
	trailingComma: 'none',
	bracketSpacing: true,
	tabWidth: 4,
	useTabs: true,
	arrowParens: 'always',
	endOfLine: 'auto',
	plugins: ['@ianvs/prettier-plugin-sort-imports'],
	importOrder: [
		'.css$',
		'',
		'<TYPES>',
		'<TYPES>^[.]',
		'',
		'^(react/(.*)$)|^(react$)',
		'',
		'<THIRD_PARTY_MODULES>',
		'',
		'^[./]'
	]
}

module.exports = config

```


   
