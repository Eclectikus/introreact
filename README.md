# Intro REACT

Revisando la documentación de [**`React`**](https://reactjs.org/) y más específicamente de los principales tutoriales disponible:

- [**Tutorial: Introducción a React**](https://es.reactjs.org/tutorial/tutorial.html)
- [**Create React App**](https://create-react-app.dev/docs/getting-started)
- [**Storybook for React tutorial**](https://www.learnstorybook.com/intro-to-storybook/react/en/get-started/)
- [**Redux tutorial**](https://redux.js.org/tutorials/essentials/part-1-overview-concepts)

:warning: Esto no es un *tutorial de un tutorial*, es simplemente una colección de recursos y rutinas útiles para seguir la documentación y probar los ejemplos que se usan en las diferentes *documentaciones*. Aunque son notas para mi uso personal, las comparto por si fueran de ayuda para aquellos que utilicen un entorno de desarrollo similar al mío. 

## Recursos

Puedes (y deberías) consultar más abajo el [README.md original](#readmemd-original) (en inglés).

### Mi entorno de desarrollo

- [**`Visual Studio Code`**](https://code.visualstudio.com/)
- [**`Git`**](https://git-scm.com/) - [**`Github`**](https://github.com/Eclectikus) - [**`GitHub Desktop`**](https://desktop.github.com/) **/** [**`TortoiseSVN`**](https://osdn.net/projects/tortoisesvn/)
- [**`PowerShell`**](https://docs.microsoft.com/es-es/powershell/)
- [**`Scoop`**](https://scoop.sh/)
- [**`npm`**](https://www.npmjs.com/) - [**`npx`**](https://www.npmjs.com/package/npx) **/** [**`yarn`**](https://yarnpkg.com/)

### PowerShell

Aunque en principio es posible utilizar el **`CLI`** que tengas integrado en tu propio **`IDE`**, yo he utilizado aquí **`PowerShell 5.1`** ([Docs](https://docs.microsoft.com/en-us/powershell/scripting/how-to-use-docs?view=powershell-5.1)).

Los comandos centrales son:

```PowerShell
# Crear App
npx create-react-app <nombre>
cd <nombre>

## Iniciar App
# npm:
npm start
# yarn:
yarn start

# Crear Storybook
npx -p @storybook/cli sb init

## Iniciar Storybook
# yarn:
yarn storybook

## Iniciar test
yarn test

## Instalar dependencias `Redux`
yarn add react-redux redux
```

Estos tres comandos (**`yarn start`**, **`yarn storybook`** y **`yarn test`**) ocupan tres pestañas y por tanto debemos habilitar una 4ª pestaña para usar libremente otros comandos que puedas necesitar.

Para simplificar el proceso he creado dos `scripts` que automatizan el inicio. Uno para ir al directorio de desarrollo:

```PowerShell
# D:\Developer\WPSscripts\webdev.ps1

# Ir al directorio de trabajo, en mi caso:
d:
cd developer\miswebs\introreact
```

Y otro para preparar las cuatros pestañas necesarias en el directorio de trabajo, y renombrarlas convenientemente:

```PowerShell
# D:\Developer\WPSscripts\introreact.ps1

# 4 tabs

# Ventana de aplicación
$psise.PowerShellTabs[0].DisplayName  = ‘App’

# Ventana de Storybook
$psISE.PowerShellTabs.Add()
$psise.PowerShellTabs[1].DisplayName  = ‘Storybook’

# Ventana de test
$psISE.PowerShellTabs.Add()
$psise.PowerShellTabs[2].DisplayName  = ‘Test’

# Ventana de comandos
$psISE.PowerShellTabs.Add()
$psise.PowerShellTabs[3].DisplayName  = ‘Comandos’

# Run script `webdev` vía el comando `Invoke`

$psISE.PowerShellTabs.SetSelectedPowerShellTab($psISE.PowerShellTabs[0])
& "D:\Developer\WPSscripts\webdev.ps1"
# > yarn start

$psISE.PowerShellTabs[1].Invoke('webdev')
# > yarn storybook

$psISE.PowerShellTabs[2].Invoke('webdev')
# > yarn test

$psISE.PowerShellTabs[3].Invoke('webdev')
# > whatever

$psISE.PowerShellTabs.SetSelectedPowerShellTab($psISE.PowerShellTabs[3])

```

Una vez iniciados, no encuentro manera de parar los servidores locales desde **`PowerShell`** (`Ctrl+C` no funciona), así que lo hago *a las bravas*:

```PowerShell
# Puerto de la propia App: http://localhost:3000
npx kill-port 3000
# Puerto de `Storybook`: http://localhost:6006
npx kill-port 6006
```

---

## README.md original

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `yarn build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
