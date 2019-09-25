# 代码评审

代码质量包括功能性代码质量和非功能性代码质量，功能质量大多通过测试能够去发现问题，非功能性代码质量用户不能直接体验到这种质量的好坏，代码质量不好，最直接的“受害者”是开发者或组织自身，因为代码质量好坏直接决定了软件的可维护性成本的高低。代码质量应该更多的应该从可测性，可读性，可理解性，容变性等代码可维护性维度去衡量，其中 CodeReview 是保证代码质量非常重要的一个环节，建立良好的 CodeReview 规范与习惯，对于一个技术团队是一件非常重要核心的事情，没有 CodeReview 的团队没有未来。

每次项目开发自测完成后，通常会组织该小组开发人员集体进行代码 review，代码 review 一般 review 代码质量以及规范方面的问题，另外需要关注的是每一行代码变更是否与本次需求相关，如果存在搭车发布或者代码重构优化，需要自行保证测试通过，否则不予发布。

CodeReview 重点关注如下事情：

1. 确认代码功能：代码实现的功能满足产品需求，逻辑的严谨和合理性是最基本的要求。同时需要考虑适当的扩展性，在代码的可扩展性和过度设计做出权衡，不编写无用逻辑和一些与代码功能无关的附加代码。

2. 编码规范：以集团开发规约、静态代码规约为前提，是否遵守了编码规范，遵循了最佳实践。除了形式上的要求外，更重要的是命名规范。目标是提高代码的可读性，降低代码可维护性成本。

3. 潜在的BUG：可能在最坏情况下出现问题的代码，包括常见的线程安全、业务逻辑准确性、系统边界范围、参数校验，以及存在安全漏洞\(业务鉴权、灰产可利用漏洞\)的代码。。

4. 文档和注释：过少（缺少必要信息）、过多（没有信息量）、过时的文档或注释，总之文档和注释要与时俱进，与最新代码保持同步。其实很多时候个人觉得良好的变量、函数命名是最好的注释，好的代码胜过注释。

5. 重复代码：当一个项目在不断开发迭代、功能累加的过程中，重复代码的出现几乎是不可避免的，通常可以通过PMD工具进行检测。类型体系之外的重复代码处理通常可以封装到对应的Util类或者Helper类中，类体系之内的重复代码通常可以通过继承、模板模式等方法来解决。

6. 复杂度：代码结构太复杂（如圈复杂度高），难以理解、测试和维护。

7. 监控与报警：基于产品的需求逻辑，需要有些指标来证明业务是正常work的，如果发生异常需要有监控、报警指标通知研发人员处理，review业务需求对应的监控与报警指标也是Code  Review的重点事项。

8. 测试覆盖率：编写单元测试，特别是针对复杂代码的测试覆盖是否足够。

实际上维护单元测试的成本不比开发成本低，这点团队目前做的的不到位。

针对以上每次代码review所涉及到的经典案例会统一输出到文档里，大家可以共同学习避免编写出同样的Ugly Code。
