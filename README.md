# eslint-config-pawvue

[**NPM**](https://www.npmjs.com/package/eslint-config-pawvue)
```console
npm i -D eslint-config-pawvue
```

## Config details:

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
  ],

  'extends': [
    'plugin:vue/essential',
    'eslint:recommended',
    '@vue/prettier',
    'prettier'
  ]
```
