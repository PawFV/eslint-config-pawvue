# eslint-config-pawvue
This configuration autoFixes the casing of your vue components with prettier and eslint. And indents better your html.
For ex: You have:
```html
<nav-bar-modal>
```
<sup>after formatting on save: </sup>
```html
<NavBarModal>
```
So, if you use vs-code with the components will be shown in green color, thus making it easier to read and work with.

## How to install
[**NPM**](https://www.npmjs.com/package/eslint-config-pawvue)
```console
npm i -D eslint-config-pawvue
```

Now in your `.eslintrc`
```js
{
  "extends": ["eslint-config-pawvue"]
}
```

## Recommended vs-code config


<sup>`Settings (JSON)`</sup>
```json  
 "editor.formatOnSave": true
 "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
 "editor.defaultFormatter": "esbenp.prettier-vscode"
```

### My .prettierrc config if you need it (Just copy it).

<sup>`.eslintrc`</sup>
```js
{
  "singleQuote": true,
  "semi": false,
  "tabWidth": 2,
  "quoteProps": "preserve",
  "trailingComma": "none",
  "endOfLine": "auto",
  "arrowParens": "avoid",
  "htmlWhitespaceSensitivity": "ignore"
}

```

### eslint-config-pawvue Config details:
#### These are the default configurations that come in this eslint package.

```js
root: true,

  env: {
    node: true
  },

  extends: [
    'plugin:vue/essential',
    'eslint:recommended',
    '@vue/prettier',
    'prettier'
  ],

  parserOptions: {
    parser: 'babel-eslint',
    ecmaVersion: 2020,
    sourceType: 'module'
  },

  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'vue/component-definition-name-casing': ['error', 'PascalCase'],
    'vue/component-name-in-template-casing': [
      'error',
      'PascalCase',
      { registeredComponentsOnly: false }
    ],
    'vue/html-end-tags': 'error',
    'vue/html-self-closing': [
      'error',
      {
        html: {
          'void': 'always',
          normal: 'always',
          component: 'always'
        },
        svg: 'always',
        math: 'always'
      }
    ],
    'prettier/prettier': [
      'error',
      { htmlWhitespaceSensitivity: 'css', parsers: ['vue'], printWidth: 80 }
    ]
  },

  overrides: [
    {
      files: [
        '**/__tests__/*.{j,t}s?(x)',
        '**/tests/unit/**/*.spec.{j,t}s?(x)'
      ],
      env: {
        jest: true
      }
    },
    {
      files: [
        '**/__tests__/*.{j,t}s?(x)',
        '**/tests/unit/**/*.spec.{j,t}s?(x)'
      ],
      env: {
        jest: true
      }
    }
  ]
```
