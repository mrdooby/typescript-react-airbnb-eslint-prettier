For airbnb installs and peer deps
https://blog.logrocket.com/linting-typescript-using-eslint-and-prettier/

npm i -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb-typescript eslint-plugin-jest
npx install-peerdeps --dev eslint-config-airbnb
npm i -D prettier eslint-config-prettier eslint-plugin-prettier

For eslint and prettier config files
https://www.alexey-nikiforov.name/setup-react-app-with-typescript-eslint-and-prettier

// package.json
"scripts": {
  ...
  "lint": "eslint src", // just check errors
  "lint-fix": "eslint src --quiet --fix" // fix lint errors
}

// .prettierrc
{
  "arrowParens": "always",
  "singleQuote": false,
  "printWidth": 100,
  "jsxBracketSameLine": false,
  "trailingComma": "none"
}

// .eslintignore
.config
node_modules/*
config/*
public/*
scripts/*
src/react-app-env.d.ts
src/reportWebVitals.ts

// .eslintrc
{
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true,
      "useJSXTextNode": true
    },
    "ecmaVersion": 2018,
    "sourceType": "module",
    "project": "./tsconfig.json"
  },
  "extends": [
    "airbnb-typescript",
    "airbnb/hooks",
    "plugin:@typescript-eslint/recommended",
    "plugin:jest/recommended",
    "prettier",
    "prettier/react",
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
  ],
  "plugins": ["react", "react-hooks", "@typescript-eslint", "jest"],
  "env": {
    "browser": true,
    "es6": true,
    "jest": true
  },
  "globals": {
    "Atomics": "readonly",
    "SharedArrayBuffer": "readonly"
  },
  "rules": {
    "linebreak-style": "off",
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "prettier/prettier": [
      "error",
      {
        "endOfLine": "auto"
      }
    ],
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "js": "never",
        "jsx": "never",
        "ts": "never",
        "tsx": "never"
      }
    ]
  }
}
