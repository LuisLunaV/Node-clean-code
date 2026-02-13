# Configuracion inicial

1. Generamos el archivo tsconfig.json

```
tsc --init
```

- 1.1 Opciones de configuracion personalizada para mi:

```
{
    "target": "es2016",
    "module": "commonjs",
    "rootDir": "src",
   -> "outDir": "dist/",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
  ->  "noImplicitAny": true,
    "skipLibCheck": true
}
```

2. Instalar dependencias de desarrollo

```
npm i --save-dev nodemon rimraf typescript ts-node
```
o
```
pnpm add --save-dev nodemon rimraf typescript ts-node

```

3. Generamos nuestro archivo nodemon.json:
- 3.1 Para npm: 
```
{
  "watch": ["src"],
  "ext": ".ts,.js",
  "ignore": [],
  "exec": "npx ts-node ./src/app.ts"
}
```

- 3.2 para pnpm:
```
{
  "watch": ["src"],
  "ext": ".ts,.js",
  "ignore": [],
  "exec": "pnpm exec ts-node ./src/app.ts"
}
```

4. Modificaamos nuestro ```script``` del package.json:
```
    "scripts": {
    "dev": "nodemon",
    "build": "rimraf ./dist && tsc",
    "start": "npm run build && node dist/app.js"
  },
```
## Proyecto de Arquitectura Limpia con NodeJS

### Instalación

1. Clonar archivo **.env.template** y renombrar a **.env**.
2. Instalar dependencias.
```bash
npm install
```
3. Levantar la base de datos
```bash
docker-compose up -d
```

4. Ejecutar proyecto en modo desarrollo
```bash
npm run dev
```


