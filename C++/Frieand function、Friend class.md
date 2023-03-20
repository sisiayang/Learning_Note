### Frieand
概念：  
在定義 class 時，privacy 中的 member 只能被相同 class 中的其他成員存取，但有時我們會希望讓外部成員存取這些 privacy member ( maybe 效能考量？)  
此時可以設定 friend，被設為 friend 的外部 function & class 可以存取自家 privacy member！  
* friend function
  ```C++
  class SampleClass{
    public:
      friend int plus(SampleClass&);
    private:
      int p;
      int q;
  }
  
  int plus(SampleClass &c){
    return c.p + c.q
  }
  ```
  
* friend class
  ```C++
  class SampleClass{
    public:
      friend class SampleClass_2;
    private:
      int p;
      int q;
  }
  
  class SampleClass_2{
    public:
      void func1(SampleClass &c){
        p_plus_q = c.p + c.q;
      }
    private:
      int p_plus_q;
  }
  ```
