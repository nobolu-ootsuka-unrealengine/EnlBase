





--------------------------------------------------------------------------------------------------------------------
----------------------------------------------JPN START -------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------






#PDフロントエンドベースプロジェクト

Perficientデジタルフロントエンドベースプロジェクトは、コンセプトの証明のためのサンプルまたはスタータープロジェクトであり、Perficient Digitalでプロジェクトのフロントエンドコードを構造化するためのリファレンスガイドです。物事が急激に変化し、単一の基盤がすべてのプロジェクトに適合しないので、石で設定されていません。

**詳細については、[Perficient Digital Front End Standards]（https://github.com/EnlightenAgency/EnlBase/wiki/Enlighten-Front-End-Standards）Wikiを参照してください。**

###推奨ファイル構造：

    | -Dist - 配布ファイルまたはビルドファイル。生成されたコードのみがdistフォルダに属します。
    | -Src - 開発ファイル
        | -css
        | - イメージ
        | -js
    | - ドキュメント - ドキュメントまたは情報ファイル
    | - テスト - 単体テスト

＃＃＃クイックスタート
1.基本プロジェクトgit repoをダウンロードします。
2. `npm install`を実行します。
3.すべての名前空間ファイルの名前を「ENL.base.js」、「ENL.init.js」、「ENL.styles.scss」に変更します。名前空間をプロジェクトの新しい名前空間（つまり、 `THF.styles.scss`、` UDR.base.js`、 `UMA.init.js`など）に変更します。
4.プロジェクト全体を通して、特にGulpfile.jsと `index.html`の名前空間ファイルへの参照をすべて変更します。
5.名前空間のルートオブジェクトをJavaScript（ `index.html`で定義され、` ENL.base.js`で設定され、 `ENL.init.js`で参照されます）で変更します。 、ページ、またはutils）
6. `gulp`を実行します。
7。 ...
8.利益

###ルートに属するファイル：

  - `.git`（または他のソースコントロール）
  - `.gitignore`（gitを使用している場合）
  - `README.md` - プロジェクトノート、セットアップ指示、変更履歴
  - `package.json` - ノードの依存関係とビルドツール用
  - `Gulpfile.js（またはGruntfile.js）` - ビルドツールファイル
  - `.eslintrc`（eslintルールの場合 - eslintを使用している場合）

###ソース管理するべきではないファイル：

  - `/ node_modules` - ノードの依存関係とビルドツール用
  - `/ bower_components` - クライアントパッケージにbowerを使用する場合
  - `/ dist` - ソースコントロールをデプロイメントに使用しない限り、コンパイルされたバージョンはソース管理されていない可能性があります

###ノードのバージョン管理

    最後に知られている作業（2011/11/22）：
     - ノード：v6.9.1（LTS）
    https://github.com/nodejs/LTS#lts_schedule
         - npm：3.10.5
         - https://www.npmjs.com/package/npm

    スイッチノードのバージョン（NVMを使用） - "nvm use [version]"注：必要なノードのバージョンがインストールされていない場合は、 "nvm install [version]"
アップグレード/ダウングレードNPM - 「npm install -g npm @ [version]」

###インストール：

  - `npm install`を実行して、` package.json`ファイル経由でgulpパッケージをインストールします。
  - サイトの構築に必要な依存関係を取得する方法については、[Gulp Setup]（https://github.com/EnlightenAgency/EnlBase/wiki/Gulp-Setup）を参照してください。

### Dev依存関係の定義

- gulp：タスクやビルドのランナーで、CSSやJavaScriptの縮小、ファイル圧縮などのタスクを自動化できます。
- https://github.com/gulpjs/gulp/tree/master/docs
- gulp-autoprefixer：CSSプロパティにverdo prefixes（-webkit-、-mos-、-ms-）オプションを追加することで、ブラウザ間の互換性を保証します
- https://github.com/postcss/autoprefixer
- gulp-concat：ファイルは、gulp.src関数で指定された順序で連結されます（例：return gulp.src（['./ lib / file3.js'、 './lib/file1.js' 、 './lib/file2.js']））
- https://github.com/contra/gulp-concat
- gulp-eslint：コードlintingは、特定のスタイルガイドラインに従わない問題のあるパターンやコードを見つけるために使用されます。
- https://www.npmjs.com/package/gulp-eslint
- http://eslint.org/docs/about/
- gulp-filesize：人間が読めるString形式のファイルをコンソールにログ出力する拡張機能。
- https://github.com/Metrime/gulp-filesize
- gulp-imagemin：GIF、JPEG、PNG、SVGイメージを圧縮する
- https://www.npmjs.com/package/gulp-imagemin
- gulp-livereload：CSS、イメージファイルなどを保存した後、自動的にブラウザを更新します。
- https://www.npmjs.com/package/gulp-livereload
- gulp-load-plugins：パッケージの依存関係からgulpプラグインを読み込んで、選択したオブジェクトにそれらを添付します。
- https://www.npmjs.com/package/gulp-load-plugins
- gulp-sass：SASSファイルをCSSファイルにコンパイルする
- https://www.npmjs.com/package/gulp-sass
- gulp-sourcemaps：あなたのCSSスタイルをdistのコンパイル済み.cssの代わりに正しい.scssファイルにマップします。例：ブラウジングコンソールは、あなたのボディスタイルがstyles.css行106ではなくglobal.scss 28行から来ていることを明らかにします。これにより、あなたのスタイルを「デバッグ」の方がずっと簡単に追跡できます。
- https://www.npmjs.com/package/gulp-sourcemaps
- gulp-svg-sprite：複数のSVGファイルを取り込んで最適化し、いくつかの種類のSVGスプライトにベイク処理するsvg-spriteをラップするGulpプラグインです。
- https://github.com/jkphl/gulp-svg-sprite
- gulp-uglify：JSファイルを縮小する
- https://www.npmjs.com/package/gulp-uglify
- gulp-util：gulpプラグインのユーティリティ（gutil.log、gutil.replaceExtension）
- https://www.npmjs.com/package/gulp-util
- gulp-webserver：LiveReloadを使用してローカルWebサーバーを実行するGulpプラグイン
- https://www.npmjs.com/package/gulp-webserver
- imagemin-gifsicle：画像最適化のオプションを追加しました - g












--------------------------------------------------------------------------------------------------------------------
----------------------------------------------JPN END -------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------



--------------------------------------------------------------------------------------------------------------------
----------------------------------------------ENG -------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------





#PD Front End Base Project

The Perficient Digital Front End Base Project is a sample or starter project for proof of concept and a reference guide for structuring a project's front end code at Perficient Digital.  It is not set in stone, as things change too fast, and a single base will not fit all projects.  

**See the [Perficient Digital Front End Standards](https://github.com/EnlightenAgency/EnlBase/wiki/Enlighten-Front-End-Standards) Wiki for more details.**

###Recommended File Structure:

    |-Dist - distribution or build files, only generated code belongs in the dist folder
    |-Src - development files
        |-css
        |-images
        |-js
    |-Docs - documentation or information files
    |-Tests - unit tests

###Quick Start
1. Download base project git repo
2. Run `npm install`
3. Rename all namespaced files `ENL.base.js`, `ENL.init.js`, `ENL.styles.scss`; changing the namespace to the project's new namespace (i.e. `THF.styles.scss`, `UDR.base.js`, `UMA.init.js`, etc.)
4. Change all references to namespaced files throughout project, particularly `Gulpfile.js` and `index.html`
5. Change the namespaced root object in JavaScript (defined in `index.html`, set in `ENL.base.js`, and referenced in `ENL.init.js`; it may also be extended in other files such as components, pages, or utils)
6. Run `gulp`
7. ...
8. Profit

###Files that belong in the root:

 - `.git` (or other source control)
 - `.gitignore` (if using git)
 - `README.md` - project notes, setup instructions, changelog
 - `package.json` - for Node dependencies and build tools
 - `Gulpfile.js (or Gruntfile.js)` - build tool files
 - `.eslintrc` (for eslint rules - if using eslint)

###Files that should not be source controlled:

 - `/node_modules` - for Node dependencies and build tools
 - `/bower_components` - if using bower for client packages
 - `/dist` - the compiled version will likely not be source controlled unless using source control for deployment

###Node Versioning

    Last known Working (11/22/2016):
    	- node: v6.9.1 (LTS)
    		https://github.com/nodejs/LTS#lts_schedule
        - npm: 3.10.5
        	- https://www.npmjs.com/package/npm

    Switch Node Version (using NVM) - "nvm use [version]"  NOTE: If desired node version is not installed, install it using "nvm install [version]"
	Upgrade/Downgrade NPM - "npm install -g npm@[version]"

###Installation:

 - `npm install` to install the gulp packages via the `package.json` file
 - See the [Gulp Setup](https://github.com/EnlightenAgency/EnlBase/wiki/Gulp-Setup) for information on getting dependencies necessary for building the site.

###Dev Dependency Definitions

	- gulp: A task/build runner that can automate tasks like, CSS and JavaScript minification, file compression, etc.
		- https://github.com/gulpjs/gulp/tree/master/docs
	- gulp-autoprefixer: Adds verdor prefixes (-webkit-, -mos-, -ms-) options to CSS properties to help ensure cross-browser compatibility
		- https://github.com/postcss/autoprefixer
	- gulp-concat: Files will be concatenated in the order that they are specified in the gulp.src function (eg. return gulp.src(['./lib/file3.js', './lib/file1.js', './lib/file2.js']))
		- https://github.com/contra/gulp-concat
	- gulp-eslint: Code linting is used to find problematic patterns or code that doesn’t adhere to certain style guidelines.
		- https://www.npmjs.com/package/gulp-eslint
		- http://eslint.org/docs/about/
	- gulp-filesize: Extension to log filesizes in human readable Strings to the console.
		- https://github.com/Metrime/gulp-filesize
	- gulp-imagemin: Compresses GIF, JPEG, PNG, and SVG images
		- https://www.npmjs.com/package/gulp-imagemin
	- gulp-livereload: Automatically refreshes browser after saving CSS, image files, etc.
		- https://www.npmjs.com/package/gulp-livereload
	- gulp-load-plugins: Loads gulp plugins from package dependencies and attaches them to an object of your choice.
		- https://www.npmjs.com/package/gulp-load-plugins
	- gulp-sass: Compiles SASS files into CSS file
		- https://www.npmjs.com/package/gulp-sass
	- gulp-sourcemaps: Maps your CSS styles to the correct .scss file instead of the compiled .css in dist. Example: The browswer console will reveal that your body style is coming from global.scss line 28 instead of styles.css line 1064. This makes tracking down your styles for "debugging" much easier.
		- https://www.npmjs.com/package/gulp-sourcemaps
	- gulp-svg-sprite: Gulp plugin wrapping around svg-sprite which takes a bunch of SVG files, optimizes them and bakes them into SVG sprites of several types.
		- https://github.com/jkphl/gulp-svg-sprite
	- gulp-uglify: Minifies JS files
		- https://www.npmjs.com/package/gulp-uglify
	- gulp-util: Utilities for gulp plugins (gutil.log, gutil.replaceExtension)
		- https://www.npmjs.com/package/gulp-util
	- gulp-webserver: Gulp plugin to run a local webserver with LiveReload
		- https://www.npmjs.com/package/gulp-webserver
	- imagemin-gifsicle: Added options for image optimization - gifs
		- https://github.com/imagemin/imagemin-gifsicle
	- imagemin-mozjpeg: Added options for image optimization - jpeg
		- https://www.npmjs.com/package/mozjpeg
	- imagemin-optipng:Added options for image optimization - png
		- https://www.npmjs.com/package/imagemin-optipng
	- imagemin-pngquant: Added options for image optimization - png
		- https://www.npmjs.com/package/imagemin-pngquant
	- imagemin-svgo: Added options for image optimization - svg
		- https://www.npmjs.com/package/imagemin-svgo
	- map-stream: Create a through stream from an asyncronous function.
		- https://www.npmjs.com/package/map-stream
	- merge-stream: Create a stream that emits events from multiple other streams.
		- https://www.npmjs.com/package/merge-stream 
