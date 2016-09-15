#狀態模式(State Pattern) 
定義：Allow an object to alter its behavior when its internal state changes. The object will appear to change its classes.（當一個對象內在狀態改變時允許其改變行為，這個對象看起來像改變了其類。）  


 狀態模式的核心是封裝，狀態的變更引起了行為的變更，從外部看起來就好像這個對象對應的類發生了改變一樣。狀態模式的通用類圖如圖所示。  
![Alt text](state.jpg "狀態模式類圖")

 我們先來看看狀態模式中的3個角色。

- State抽象狀態角色：接口或抽象類，負責對象狀態定義，並且封裝環境角色以實現狀態切換。
- ConcreteState具體狀態角色：每一個具體狀態必須完成兩個職責：本狀態的行為管理以及趨向狀態處理，通俗地說，就是本狀態下要做的事情，以及本狀態如何過渡到其他狀態。
- Context環境角色：定義客戶端需要的接口，並且負責具體狀態的切換。


#狀態模式的應用
##1.狀態模式的優點
 * 結構清晰：避免了過多的switch...case或者if...else語句的使用，避免了程序的複雜性，提供系統的可維護性。
 * 遵循設計原則：很好地體現了開閉原則和單一職責原則，每個狀態都是一個子類，你要增加狀態就要增加子類，你要修改狀態，你只修改一個子類就可以了。
 * 封裝性非常好：這也是狀態模式的基本要求，狀態變換放置到類的內部來實現，外部的調用不用知道類內部如何實現狀態和行為的變換。


##2.狀態模式的缺點 
狀態模式既然有優點，那當然有缺點了。但只有一個缺點，子類會太多，也就是類膨脹。如果一個事物有很多個狀態也不稀奇，如果完全使用狀態模式就會有太多的子類，不好管理。  


##3.狀態模式的使用場景
 * 行為隨狀態改變而改變的場景。
 * 條件、分支判斷語句的替代者：在程序中大量使用switch語句或者if判斷語句會導致程序結構不清晰，邏輯混亂，使用狀態模式可以很好地避免這一問題，它通過擴展子類實現了條件的判斷處理。
 
##4.狀態模式的注意事項
狀態模式適用於當某個對象在它的狀態發生改變時，它的行為也隨著發生比較大的變化，也就是說在行為受狀態約束的情況下可以使用狀態模式，而且使用時對象的狀態最好不要超過5個。

 