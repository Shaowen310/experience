# Vue Config

## eslint

### Disable \`no-unused-vars\` error

```json

{
  "eslintConfig": {
    "extends": [
      "plugin:vue/vue3-essential",
      "eslint:recommended"
    ],
    "rules": {
      "no-unused-vars": [
        "warn",
        {
          "argsIgnorePattern": "^_"
        }
      ],
      "vue/no-unused-vars": [
        "warn",
        {
          "ignorePattern": "^_"
        }
      ]
    }
}
```
