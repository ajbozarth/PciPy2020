# SciPy 2020 Poster

[![Binder](http://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ajbozarth/SciPy2020/master?urlpath=lab)

## Creating a extension

1. Open a console in lab and run: `cookiecutter https://github.com/jupyterlab/extension-cookiecutter-ts`

2. Fill out the prompts and then in the lab file browser open the new dir

3. Edit `package.json` adding the following `dependencies`:

   ```
   "@jupyterlab/apputils": "^2.0.0",
   "@jupyterlab/docregistry": "^2.0.0",
   "@jupyterlab/notebook": "^2.0.0",
   "@lumino/disposable":  "^1.3.5"
   ```

3. Edit `src/index.ts` and add the following import: `import {ButtonExtension} from "./button";`
and add the follwoing to the activate function:

   ```
   let buttonExtension = new ButtonExtension();
   app.docRegistry.addWidgetExtension('Notebook', buttonExtension);
   ```

4. Move the `button.ts` file into the `src` dir

5. In the console from step 1 run:

   ```
   jlpm
   jlpm build
   jupyter labextension install .
   ```

