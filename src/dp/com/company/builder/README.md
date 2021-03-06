#建造者模式(Builder Pattern) 
定義：Separate the construction of a complex object from its representation so that the same construction process can create different representations. 將一個複雜對象的構建與它的表示分離，使得同樣的構建過程可以創建不同的表示。     

建造者模式的通用類圖如下圖：  
![Alt text](builder.jpg "建造者模式類圖")

在建造者模式中，有如下四個角色：

- Product產品類：通常是實現了模板方法模式，也就是有模板方法和基本方法，這個參考上一章節的模板方法模式。在例子中，BenzModel和BMWModel就屬於產品類。
- Builder抽象建造者：規範產品的組建，一般是由子類實現。在例子中，CarBuilder屬於抽象建造者。 
- ConcreteBuilder具體建造者：實現抽象類定義的所有方法，並且返回一個組件好的對象。在例子中，BenzBuilder和BMWBuilder就屬於具體建造者。
- Director導演：負責安排已有模塊的順序，然後告訴Builder開始建造，在上面的例子中就是我們的老大，牛叉公司找到老大，說我要這個，這個，那個類型的車輛模型，然後老大就把命令傳遞給我，我和我的團隊就開始拼命的建造，於是一個項目建設完畢了。 

#建造者模式的應用
##建造者模式的優點
 * 封裝性。使用建造者模式可以使客戶端不必知道產品內部組成的細節，如例子中我們就不需要關心每一個具體的模型內部是如何實現的，產生的對象類型就是CarModel。 
 * 建造者獨立，容易擴展。
 * 便於控制細節風險。由於具體的建造者是獨立的，因此可以對建造過程逐步細化，而不對其他的模塊產生任何影響。 
 
##建造者模式的使用場景
 * 相同的方法，不同的執行順序，產生不同的事件結果時，可以採用建造者模式。
 * 多個部件或零件,都可以裝配到一個對象中，但是產生的運行結果又不相同時，則可以使用該模式。 
 * 產品類非常複雜，或者產品類中的調用順序不同產生了不同的效能，這個時候使用建造者模式是非常合適。 
 * 在對象創建過程中會使用到系統中的一些其它對象，這些對象在產品對象的創建過程中不易得到時，也可以採用建造者模式封裝該對象的創建過程。該種場景，只能是一個補償方法，因為一個對象不容易獲得，而在設計階段竟然沒有發覺，而要通過創建者模式柔化創建過程，本身已經違反設計最初目標。
 
##建造者模式的注意事項
建造者模式關注的是的零件類型和裝配工藝（順序），這是它與工廠方法模式最大不同的地方，雖然同為創建類模式，但是注重點不同。  

#建造者模式的擴展
已經不用擴展了，因為我們在汽車模型製造的例子中已經對建造者模式進行了擴展，引入了模板方法模式，可能大家會比較疑惑，為什麼在其他介紹設計模式的書籍上創建者模式並不是這樣說的，讀者請注意，建造者模式中還有一個角色沒有說明，就是零件，建造者怎麼去建造一個對象？是零件的組裝，組裝順序不同對象效能也不同，這才是建造者模式要表達的核心意義，而怎麼才能更好的達到這種效果呢？引入模板方法模式是一個非常簡單而有效的辦法。  
大家看到這裡估計就開始犯嘀咕了，這個建造者模式和工廠模式非常相似呀，Yes，是的，是非常相似，但是記住一點你就可以遊刃有餘的使用了：建造者模式最主要功能是基本方法的調用順序安排，也就是這些基本方法已經實現了，通俗的說就是零件的裝配，順序不同產生的對象也不同；而工廠方法則重點是創建，創建零件時它的主要職責，你要什麼對象我創造一個對象出來，組裝順序則不是他關心的。  

#最佳實踐
再次說明，在使用建造者模式的時候考慮一下模板方法模式，別孤立的思考一個模式，僵化的套用一個模式會讓受害無窮！

        