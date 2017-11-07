### 改变fn内部this的情况

```javascript
    function A (name){
        this.name = name    
    }

    function B(){
        A.call(this,arguments)
        // call 和 apply 都能改变this指向
        // bind 不能
    }

    new B()

```