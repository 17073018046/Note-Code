## export和import
### export导出

```
export var name="李四";
```

### import导入

```
import { name } from "/.a.js"

alert(name)//可以弹出来“李四”
```
### 多个变量
```
 var name1="李四";
 var name2="张三";
 export { name1 ,name2 }
```
导入
```
import { name1 , name2 } from "/.a.js" 
```
## export与export default

- export与export default均可用于导出常量、函数、文件、模块等
- 你可以在其它文件或模块中通过import+(常量 | 函数 | 文件 | 模块)名的方式，将其导入，以便能够对其进行使用
- 在一个文件或模块中，export、import可以有多个，export default仅有一个
- 通过export方式导出，在导入时要加{ }，export default则不需要