
# Vite React Typescript Template

A fairly minimal setup 

## Init

```bash
npm init --yes
```

## Package type set to "module"

```bash
npm pkg set type="module"
```

Use newer ES module loader

## Install React

```bash
npm install react react-dom
```

## Install Typescript

```bash
npm install -D @types/react @types/react-dom typescript
```

## Install vite

```bash
npm install -D vite @vitejs/plugin-react
```

## Create Vite config

```javascript
// vite.config.ts
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
	plugins: [react()]
})
```

## Create index.html

* Vite conventions state that `index.html` should be in the root directory of the project, inline with a traditional static-server setup.
* add a `root` element where the app will be mounted
* add the react entrypoint in a script tag

```html
<div id="root"></div> 
<script type="module" src="/src/main.jsx"></script>
```

## Create react entry point

```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import { App } from './App.tsx'

ReactDOM.createRoot(document.getElementById('root')).render(
    <App />
)
```

## Setup App component

```javascript
// App.tsx
import React from 'react'

export const App = () => {
    return <div>hello world</div>
}
```

# Set dev script

```
npm pkg set scripts.dev="vite"
```