### virtual function
* 不強制子類實作，子類若不實作會以父類為主，子類若實作則以子類為主  
  ```C++
  class parents{
    public:
      virtual int return_num(int n){
        return n * 10;
      }
  }

  class child: public parents{
    public:
      virtual int returm_num(int n) override{
        return n + 10;
      }
  }
  ```

* 如果想利用 parents 的 function 結果再加以修改，可以用 parents::function_name
  ```
  class child: public parents{
    public:
      virtual int returm_num(int n) override{
        return parents::return_num(n) + 10;
      }
  }
  ```
