Template
===

* 使用 Template 的原因：reuse！
    相同功能的 function 因為型態不同，需要分開單獨寫自己的 function
    ```C++
    // 整數版本
    int Add(int a, int b){
        return a + b;
    }
    
    // 浮點數版本
    float Add(float a, float b){
        return a + b;
    }
    ```
    這樣不只要花很多時間處理資料型態的問題，幫每個不同型態都寫自己的function，還會讓 code 難以維護(重複功能太多)
    利用 template 可以達到 generic programming 的目的，讓 programmer 更專注在 algo 上而不用花時間處理 data type issue
    :::info
    有些語言本來就支援 (Java)這種多型態的自動轉換
    :::
    壞處：
    1. 報錯比較難懂 (why?)
    2. 在編譯時期每種 type 都要被實現 -> 耗時且程式會比原本想像的占空間(?)
    
* 宣告樣版
    ```C++
    template <class T>
    T myAdd(T a, T b) {
        return a + b;
    }
    ```
    呼叫這個 function 的時候，資料型態在編譯時期才會決定！
    
* Specialization template
    針對某個特定的資料型態做特殊處理的方式
    ```C++
    template<>
    class AddElements<string>{
        string element;
        public:
            ...
    };
    ```

---
* HackerRank 關於 Template 的題目：
    https://www.hackerrank.com/challenges/cpp-class-template-specialization/problem?isFullScreen=true
    ```C++
    template<class T>
    class AddElements{
        T element;
        public:
            AddElements(T arg){
                element = arg;
            }
            T add(T e1){
                return element + e1;
            }
    };

    template<>
    class AddElements<string>{
        string element;
        public:
            AddElements(string arg){
                element = arg;
            }
            string concatenate(string e1){
                return element + e1;
            }
    };
    ```