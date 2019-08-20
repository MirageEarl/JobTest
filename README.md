# 1.Why should you have minimum scope for variables?
答：1.便于我们理解变量的使用方式和来源；2.避免未知的调用或修改，降低出现错误或异常的可能性。3.保证变量作用的单一，在出现错误是只需要修改错误的地方即可。

# 2.Why should you understand performance of String Concatenation?
## 答：在Java中，字符串对象是不可变的，这意味着一旦创建它，就无法对其进行更改。因此，当我们将一个字符串与另一个字符串连接起来时，会创建一个新字符串。假设我们要进行100万次字符串连接，这对于Java来说就是一个非常大的开销，所以我们需要了解到怎样的字符串连接开销是最小的。

# 3.What are the best practices with Exception Handling?
答：1.I/O异常的处理和资源的关闭 try-with-resource；
2.抛出的异常越具体越好，例如NumberFormatException这样含义比较具体的异常，便于开发人员理解；
3.每当在方法签名中指定异常时，还应该在Javadoc中记录它。在注释中使用@throws
4.如果异常不是很具体，则该异常需要有具体的描述信息。
5.异常捕捉时，将最特定的异常放在最前面捕捉，其次是不确定的异常，如NumberFormatException 和 IllegalArgumentException。
6.不要忽略任何一个异常，无论你多么确信它永远不会发生
7.只捕捉想处理的异常，并且在捕捉后跑出自定义异常时，要将堆栈信息也打印出来

# 4.When is it recommended to prefer Unchecked Exceptions?
答：我们无法控制并可能会发生的异常，建议选择未检查的异常。

# 5.When do you use a Marker Interface?
答：当我们需要某种标记来判断默写特定的类时，我们可以创建一个标记接口，让这些类实现它。

# 6.Why are ENUMS important for Readable Code?
答：当我们定义的某个变量只能从特定的范围内选择的时候，使用枚举可以避免错误或无效的参数传入，维护人员可以获知合法参数有哪些。枚举就和模板一样，我们定义好，其他需要的方法只要使用就可以了，如果需要作出某些修改，只需要修改一处即可。

# 7.Why should you minimize mutability?
答：尽量减少变化，使得类或方法变得简单，也就是职能趋向于单一，这便于后期的维护，也能提高代码的可读性。
变化小甚至不可变，意味着线程更加安全，对象可以自由共享，这些好处都是我们应该让方法类减少变化的理由。

# 8.What is functional programming?
答：函数式编程是一种编程范式，简单的说就是输入参数，获取结果，并且不会对外部参数进行任何修改，这是一种编程方式。在调用这个函数时，我们不关心这个函数的内部是怎么执行的，只需要关注结果即可，函数对于我们而言就是一个黑盒。这也意味着，这个函数方法是可替换的，如果需要我们随时可以替换，并且不会对程序造成任何可预期的负面影响。

# 9.Why should you prefer Builder Pattern to build complex objects?
答：在创建负责类时，可能需要有多种传参，需要考虑必填项和可选项，一般我们的做法是重载构造函数，这样确实可以解决我们创建不同参数同一类的的需求，但是这样的创建方式是不统一的，并且如果对象的参数非常的多，那么会造成这个复杂类的构造函数非常的多，代码不够简洁，这时构建模式就可以将多种创建方式统一为一种，减少重载方法，提高代码的可读性。
使用生成器设计模式，如果创建对象所需的字段数量增加，我们可以拥有更易于维护的代码。它还减少了由于显式可选方法调用而传递无效值的机会

# 10.Why should you avoid floats for Calculations?
答：当小数（例如0.1）转化为浮点数是，在二进制文件中只能存储一个近似值（十进制的0.100000001490116119384765625），使用这样的数字去计算金额时，可能会造成严重的精度缺失。所以我们要尽可能的使用BigDecimal，并且最好是BigDecimal（“0.1”）而不是BigDecimal（0.1）， 因为BigDecimal（0.1）存储的结果是（0.1000000000000000055511151231257827021181583404541015625），而
BigDecimal（“0.1”）的结果就是0.1

# 11.Why should you build the riskiest high priority features first?

