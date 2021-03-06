#策略模式(Strategy Pattern) 
定義：Define a family of algorithms, encapsulate each one, and make them interchangeable.（定義一組算法，將每個算法都封裝起來，並且使它們之間可以互換。）  


策略模式的通用類圖如下圖：  
![Alt text](strategy.jpg "策略模式類圖")

策略模式使用的就是面向對象的繼承和多態機制，非常容易理解和掌握，我們再來看策略模式的三個角色。

- Context角色：起承上啟下封裝作用，屏蔽高層模塊對策略、算法的直接訪問，封裝可能存在的變化。
- Strategy抽象策略角色：策略、算法家族的抽象，通常為接口，定義每個策略或算法必須具有的方法和屬性。
- ConcreteStrategy具體策略角色：實現抽象策略中的操作，該類含有具體的算法。


#策略模式的應用
##1.策略模式的優點
 * 算法可以自由切換。
 * 避免使用多重條件判斷。
 * 擴展性良好。

##2.策略模式的缺點 
 * 策略類數量增多：每一個策略都是一個類，複用的可能性很小，類數量增多。
 * 所有的策略類都需要對外暴露。上層模塊必須知道有哪些策略，然後才能決定使用哪一種策略，這與迪米特法則是相違背的，我只是想使用一個策略，我憑什麼就要了解這個策略呢？那要你的封裝類還有什麼意義？這是原裝策略模式的一個缺點，幸運的是，我們可以使用其他模式來修正這個缺陷，如果工廠方法模式、代理模式或享元模式。

##3.策略模式的使用場景
 * 多個類只有在算法或行為上稍有不同的場景。
 * 算法需要自由切換的場景。
 * 需要屏蔽算法規則的場景。
 
##4.策略模式的注意事項
如果系統中的一個策略家族的具體策略數量超過4個，則需要考慮使用混合模式，解決策略類膨脹和對外暴露的問題，否則日後的系統維護就會變成一個燙手山芋。 