# devcontainer-templates

Templates for various devcontainers used in vscode.

## requirements
- [docker](https://docs.docker.com/get-docker)
- [vscode](https://github.com/Microsoft/vscode)
- [devcontainers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## matlab

* you need to [create a matlab account](https://de.mathworks.com/mwaccount/register)
* and to [create your license file](https://de.mathworks.com/matlabcentral/answers/235126-how-do-i-generate-a-matlab-license-file)
* Select Linux, matlab as login name and use `02:42:ac:11:00:FE` as HOST-ID)  
  ![](assets/2022-10-06-12-19-14.png)
* store it under `license/license.lic`

### usage

**Web interface:**
* execute `matlab-proxy-app`
* open <http://localhost:8888/index.html>

**Shell or File execution:**
* <Ctrl+Shift+P> run current script
* <Ctrl+Shift+P> run current selection
> NOTE: MATLAB file names must start with a letter and contain only letters, numbers or underscores.

## ocaml

> Credits to <https://github.com/johnnymn/ocaml-devcontainer>

## typescript-vue
