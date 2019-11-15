## Yarn vs Npm


https://stackshare.io/stackups/npm-vs-yarn

NPM (Node package manager) and Yarn (package manager created by Facebook)

*What is npm?* The package manager for JavaScript. npm is the command-line interface to the npm ecosystem. It is battle-tested, surprisingly flexible, and used by hundreds of thousands of JavaScript developers every day.
*What is Yarn?* 
Yarn is a new package manager that replaces the existing workflow for the npm client or other package managers while remaining compatible with the npm registry. It has the same feature set as existing workflows while operating faster, more securely, and more reliably.

[Tags · npm/npm · GitHub](https://github.com/npm/npm/tags?after=v1.0.1rc0). 1.0.0-1-rc. Mar 22 2011. 
[Tags · yarnpkg/yarn · GitHub](https://github.com/yarnpkg/yarn/tags?after=v1.0.1) Sep 5, 2017 

## Compare:
* init  / package.json
`npm init` && `yarn init`

* velocity / message
`npm install jest`  && `yarn add jest`

*1.* *Resolving:* Yarn starts resolving dependencies by making requests to the registry and recursively looking up each dependency.
*2.* *Fetching:*Next, Yarn looks in a global cache directory to see if the package needed has already been downloaded. If it hasn’t, Yarn fetches the tarball for the package and places it in the global cache so it can work offline and won’t need to download dependencies more than once. Dependencies can also be placed in source control as tarballs for full offline installs.
*3.* *Linking:* Finally, Yarn links everything together by copying all the files needed from the global cache into the local node_modules directory.

* Install
```json
{
 	  "jest": "^24.9.0",
    "react": "^16.11.0",
    "react-dom": "^16.11.0"
}
```
*  turn off wifi install
* lock file 
	* npm 采用的策略可能会导致同一 package.json文件两机，安装不同版本的安装包，可能会造成引入错误. `npm shrinkwrap` 来锁定版本。  package-lock.json appears after v5. 
	* yarn.lock

* Other commands
	* `yarn list`  `npm ls`
	* `yarn version` && `npm version`
	* `yarn why wordwrap`   
	* `yarn info wordwrap`
	* `yarn import`

文件依赖优化：在之前的版本，如果将本地目录作为依赖来安装，将会把文件目录作为副本拷贝到 node_modules 中。而在 npm5 中，将改为使用创建 symlinks 的方式来实现（使用本地 tarball 包除外），而不再执行文件拷贝。这将会提升安装速度。目前yarn还不支持。
