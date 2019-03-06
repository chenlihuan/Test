# js高级编程之代理模式
    代理模式概念:代理模式(Proxy)，为其他对象提供一种代理以控制对这个对象的访问。
    代理模式使得代理对象控制具体对象的引用，代理几乎是任何对象：比如：文件，资源，内存控件对象或者难以复制的一些东西
 #作用与注意事项
    #作用
        远程代理(一个对象将不同空间的对象进行局部代理)。
        虚拟代理(根据需要创建开销很大的对象，比如：渲染网页暂时用占位代替真图)
        安全代理(控制真实对象的访问权限).
        智能指引(调用对象处理另外一些事情，比如垃圾回收机制)。
     #注意事项
        不能滥用代理，有时候仅仅是给代码增加复杂度。
     #实战(代理需要3方)
     ex:
      function A(argument){
      this.name ="Ada";
      }
     function B(){
     }
     B.prototype.C = function(){
      new D(new A()).C("20万");
     }
     function D(A){
        this.A_name = A.name;
        this.C = function(money){
        console.log("收到来自【" + this.A_name +"】" +money  +"万");
        }
     }
    (new B).C();

