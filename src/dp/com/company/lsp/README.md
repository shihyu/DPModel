#里氏替換原則(LSP:Liskov Substitution Principle)
定義：所有引用基類（父類）的地方必須能透明地使用其子類的對象。    
  
里氏替換原則告訴我們，在軟件中將一個基類對象替換成它的子類對象，程序將不會產生任何錯誤和異常，反過來則不成立，如果一個軟件實體使用的是一個子類對象的話，那麼它不一定能夠使用基類對象。

里氏替換原則是實現開閉原則的重要方式之一，由於使用基類對象的地方都可以使用子類對象，因此在程序中儘量使用基類類型來對對象進行定義，而在運行時再確定其子類類型，用子類對象來替換父類對象。  

##里氏替換原則為良好的繼承定義了一個規範，它包含了4層定義：
 * 子類必須完全實現父類的方法。
 * 子類可以有自己的個性。
 * 覆蓋或實現父類的方法時輸入參數可以被放大。
 * 覆寫或實現父類的方法時輸出結果可以被縮小。
  
採用里氏替換原則的目的就是增強程序的健壯性，版本升級時也可以保持非常好的兼容性。即使增加子類，原有的子類還可以繼續運行。在實際項目中，每個子類對應不同的業務含義，使用父類作為參數，傳遞不同的子類完成不同的業務邏輯，非常完美。