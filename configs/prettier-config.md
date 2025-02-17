# 🎨 Prettier Configuration

Este archivo describe la configuración de **Prettier** utilizada en mis proyectos, incluyendo las reglas aplicadas y las dependencias necesarias.

## 📌 Instalación de dependencias

Para que esta configuración funcione correctamente, instala las siguientes dependencias:

```sh
npm install --save-dev prettier prettier-plugin-tailwindcss @trivago/prettier-plugin-sort-imports
```

Si usas **yarn**:

```sh
yarn add --dev prettier prettier-plugin-tailwindcss @trivago/prettier-plugin-sort-imports
```

Si usas **pnpm**:

```sh
pnpm add -D prettier prettier-plugin-tailwindcss @trivago/prettier-plugin-sort-imports
```

## 📂 Creación del archivo de configuración

Para que Prettier funcione correctamente, debes crear un archivo `.prettierrc` en la raíz del proyecto con el siguiente contenido:

```json
{
  "semi": false,
  "printWidth": 120,
  "trailingComma": "es5",
  "tabWidth": 2,
  "useTabs": false,
  "singleQuote": false,
  "jsxSingleQuote": false,
  "bracketSpacing": true,
  "importOrder": [
    "<THIRD_PARTY_MODULES>",
    "<YOUR_MODULES>",
    "^@/.*\\.tsx$",
    "^@/.*$",
    "^[./]"
  ],
  "importOrderSeparation": true,
  "importOrderSortSpecifiers": true,
  "importOrderCaseInsensitive": true,
  "importOrderGroupNamespaceSpecifiers": true,
  "plugins": [
    "@trivago/prettier-plugin-sort-imports",
    "prettier-plugin-tailwindcss"
  ]
}
```

## ⚙️ Configuración

El archivo `.prettierrc` contiene la siguiente configuración:

| Clave                                 | Valor                                                                        | Descripción                                              |
| ------------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------- |
| `semi`                                | `false`                                                                      | No usa punto y coma al final de las líneas.              |
| `printWidth`                          | `120`                                                                        | Máximo ancho de línea antes de hacer un salto.           |
| `trailingComma`                       | `"es5"`                                                                      | Agrega comas finales en ES5+.                            |
| `tabWidth`                            | `2`                                                                          | Usa 2 espacios en lugar de tabs.                         |
| `useTabs`                             | `false`                                                                      | Usa espacios en lugar de tabs.                           |
| `singleQuote`                         | `false`                                                                      | Usa comillas dobles en lugar de simples.                 |
| `jsxSingleQuote`                      | `false`                                                                      | Usa comillas dobles en JSX.                              |
| `bracketSpacing`                      | `true`                                                                       | Agrega espacio dentro de los corchetes `{ foo: "bar" }`. |
| `importOrder`                         | `[ "<THIRD_PARTY_MODULES>", "<YOUR_MODULES>", "^@/.*$", "^[./]" ]`           | Ordena imports en grupos.                                |
| `importOrderSeparation`               | `true`                                                                       | Agrega una línea en blanco entre grupos de imports.      |
| `importOrderSortSpecifiers`           | `true`                                                                       | Ordena automáticamente los imports dentro de cada grupo. |
| `importOrderCaseInsensitive`          | `true`                                                                       | Ignora mayúsculas/minúsculas al ordenar imports.         |
| `importOrderGroupNamespaceSpecifiers` | `true`                                                                       | Agrupa imports con nombres similares.                    |
| `plugins`                             | `[ "prettier-plugin-tailwindcss", "@trivago/prettier-plugin-sort-imports" ]` | Plugins adicionales para orden automático.               |
| `tailwindConfig`                      | `"./tailwind.config.ts"`                                                     | Usa un archivo de configuración de TailwindCSS.          |

## 🚀 Uso

Puedes ejecutar Prettier manualmente con:

```sh
npx prettier --write .
```

o, si prefieres configurarlo en `package.json`, agrega un script:

```json
"scripts": {
  "format": "prettier --write ."
}
```

Y luego ejecútalo con:

```sh
npm run format
```

---

📌 **Referencias**:

- [Prettier Docs](https://prettier.io/docs/en/index.html)
- [Prettier Plugin Tailwind](https://github.com/tailwindlabs/prettier-plugin-tailwindcss)
- [Sort Imports Plugin](https://github.com/trivago/prettier-plugin-sort-imports)
