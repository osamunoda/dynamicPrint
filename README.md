# dynamicPrint
Label Print App for FileMaker

(requirement) Mac, Chrome only

One of the annoying thing in FileMaker development is to prepare various layouts according to various printers or various customer's needs.
Each printer has its own characteristics. On one printer you can print well, but not on the others. Have you ever wanted to change objects position slightly before print?
If users don't have the privilege to enter into layout mode, developers of the app are called and complained.
That's the place where Dynamic Print comes in.
This approach does not resolve all these problems, but in some cases I think it's useful.
By delegating print to web browser(Chrome), FileMaker has no need to prepare layouts/scripts relating to print.
FileMaker's task is only to pass the data to Chrome. Users can define objects positions and its size freely on Chrome.
And those information ( object size and position ) is saved in Chrome's localStorage.
Users can use the same settings they defined yesterday.

-- How to pass the data from FileMaker to Chrome --  
There are two ways.
1. Drag and Drop via 'Data Source Selector'  
DataSourceSelector is a webviewer widget I made. Using this, you can generate csv data and drag and drop it into Chrome.
2. Embed the data into the code directly in FileMaker  
FileMaker exports the html file after that.  
In DEMO file, you can test these two ways.

-- How to use it --  
At first there are no styles, so all objects resides in the left top corner. Move those as you want.
There are four functions of the object.
1. Move: grasp the center of the object and drag
2. Resize: use bottom-right corner. Dragging the bottom-right corner,font-size is changed.
font-size is restricted not to be less than 14px.
3. Change writing direction( vertical - horizontal ): use right-top corner
4. Expand spacing: use left-top corner By clicking, the mode is changed. Dragging the bottom-right corner, character-spacing is changed.

-- Caveats --
1. Chrome Settings:  "Block third-party cookies" must be off/disabled ( because dynamicPrint usess localStorage )
2. When you use "Data Source Selector( WebViewer widget )" in your own file, make sure that your privilege settings enables fmurlscript.  

DEMO FILE: Customers.fmp12   
How-to-use movies: howto_1.mp4, howto_2.mp4  
In DEMO, postcard means Japanese postcard.

-------------------------------------------------------------------

FileMakerで開発するにあたり面倒なことの一つとして様々なプリンタやユーザーのニーズに合わせた印刷用レイアウトを開発者が複数用意しなければいけない、という問題があります。
プリンタにはそれぞれクセがあります。あるプリンタでうまく印刷できても他のものではダメということもあります。
印刷前にちょっとだけオブジェクト位置をずらしたい、思ったことはないでしょうか？
ユーザーがレイアウトモードに移動できる権限を持っていればいいのですが、そうでなければ開発者であるあなたが呼ばれ文句を言われることになります。
そういった問題を解決するためにdynamicPrintを作りました。これで全てが解決、という訳ではないですが、一定のケースには有効であると考えます。
印刷をブラウザ（Chrome）に任せてしまえば、印刷にまつわる様々なスクリプトやレイアウトをFileMaker側で用意する必要が無くなります。唯一の仕事はデータをChromeに渡すだけです。
ユーザーはChrome上で自由にオブジェクト位置やフォントサイズを調整できます。そしてその印刷情報はChromeのlocalStorage上に保存されます。
ユーザーは昨日定義したレイアウトで今日も同じように印刷することができるのです。

-- データの受け渡し方法 --    
２つあります。  
1.『Data Source Selector』を使いドラッグ&ドロップ  
Data Source Selectorは私が作ったWebViewer部品です。これによりCSVデータを生成することができ、そのデータをChromeにドラッグ&ドロップできるようになります。  
2.FileMaker側でデータを直接コードに埋め込み、その後、HTMLファイルとしてこれをエクスポート

デモファイルを使ってこれら２つの方法をお試しいただけます。

-- 使い方 --  
データを渡した直後の状態ではオブジェクトは全て左上の位置に重なって存在します。それらをお好きな位置に動かしてください。
各オブジェクトには次の４つの機能があります。
1. 移動：オブジェクト中心を掴んでドラッグしてください。
2. リサイズ：右下角を掴みドラッグするとフォントサイズが拡大縮小します。
3. 文字方向の変更（縦書きー横書き）：右上隅の角をクリックすることにより向きが変わります。
4. 文字間スペースの変更：左上隅をクリックするとモードが変わります。この状態で右下角をドラッグすると文字間スペースが拡大縮小します。

-- 注意点 --
1. ブラウザcookie設定："Block Third Party" の項目をdisbled/offとする必要がある（dynamicPrintがlocalStorageを使用する関係上）
2. Data Source Selector(WebViewer部品)をあなたの独自のファイルで新規にお使いになる際にはsecurityの権限設定においてfmurlscriptが有効になっていることを確認してください。   

デモファイルとしてCustomers.fmp12をお試しください。  
使い方movie: howto_1.mp4, howto_2.mp4