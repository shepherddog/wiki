???+note

	DDD的核心思想：知识驱动开发。
	
	DDD的关键过程: 是解决团队中不同岗位和角色之间，交流语言不统一的问题。

	DDD的代码实践: 不是任意的，是在 TypeDD（类型驱动开发） 模式下用 ADT（代数数据类型）准确表达领域知识的过程。

## DDD是什么

DDD 这个词儿，来自 Evans Eric 在 2003 年的一本书《Domain-Driven Design: Tackling Complexity in the Heart of Software》

在这本书中，Evans 提出了他对软件的复杂性来源的一个关键洞察——软件模型跟领域模型的不匹配，并提出他的解决方案（即 DDD）。

Evans 认为，软件模型和领域模型不匹配，让软件的复杂度不必要地增加，让软件的迭代和维护都变得过分困难，远超它们应有的复杂度。

他认为，其根本原因在于，领域专家（可以理解为业务同事）和开发团队之间缺乏通用的沟通语言，存在很多误解和曲解。

具体表现为，尽管业务专家和开发团队使用同一些词汇，比如账户、订单、优惠等，但他们脑中这些词汇的含义却可能不同。很容易出现表面上大家彼此达成一致，实质上各干各的。

软件交付后，业务同事开始责怪功能跟他们预期不符，跟最初说好的不一样。开发团队却觉得我们就是按照需求描述来的，怎么交付后对方不承认了。

他们的感受都对，也都不对。他们各自在自己的逻辑中正确，但在对方的逻辑中，同一个词却有不同的意义，从而产生了不匹配。

![](images/Pasted%20image%2020221213121311.png)

为避免上述虚假共识现象，DDD 认为，需要培养团队的 Ubiquitous Language，确保领域专家和开发团队对同一个词的理解总是相同的。

之前的模式下，业务同事和产品同事前期讨论的成果，汇总为产品需求文档（PRD）。开发人员主要是读者。

![](images/Pasted%20image%2020221213121331.png)

而 DDD 模式下，开发团队更早参与到业务讨论中，跟业务专家走得更近。每一个业务里的关键词汇，都是在讨论过程中，在所有人的见证下确立的。开发人员成为了创作者之一。

我们可以提炼出几个关键部分：

-   A major software design approach
-   Focuses on modeling software to match a domain
-   According to input from that domain's experts

我们可以看到，DDD 是一种软件设计方法，它不仅仅是团队之间的沟通技巧。它必须涉及到软件开发的部分，也就是必须跟代码有关系。并且，代码必须跟领域相匹配，而领域模型则来自领域专家们。

DDD 的核心是代码模型和领域模型的匹配关系，两者缺一不可。  

  
## DDD的常见误解

**第一类误解是，认为 DDD 跟代码实现无关。**

一些开发者看到后续的 DDD 著作，主要集中在更通用的战略设计部分，削弱了战术设计部分的比重，就误以为 DDD 的核心在于战略设计部分，甚至认为只需要战略设计部分。

这是把战略设计和战术设计对立起来。其实它们并非互斥，并不是有两种 DDD。

而是 DDD 有两个阶段：

1.  战略建模阶段，重视团队沟通和协作。这个阶段输出：Bounded Context， Context Maps 和 Ubiquitous Language 。  
    
2.  战术建模阶段，重视软件的开发和维护。这个阶段的输入是战略建模阶段的输出，输出的是交付的软件。  
    
![](images/Pasted%20image%2020221213121928.png)
  
DDD 的核心目标是交付高质量的软件，它需要全链路地考量软件开发的过程。既不能只考虑怎么写代码，忽视业务逻辑的来源的可靠性；也不能只考虑业务模型，忽视写代码的部分。缺少任何一部分，都难以有效地管理软件的复杂度，也难以保障软件的交付质量。

实际上，如果只考虑战略设计，即团队协作沟通以达成共识这块。DDD 提供的 Bounded Context， Context Maps 和 Ubiquitous Language 缺乏科学理论和实验支撑，并不是一个好的选择，并且很容易流俗于开发流程的培训活动。

失去代码支撑的战略设计，也达不到 DDD 所承诺的目标。

在论文《A new approach to the semantics of model diagrams》，作者JG Granström 写道：

> 有时，一张图比一千行代码更能说明问题。但是，可悲的是，大多数情况下，软件工程师在过了设计阶段后就放弃了图表，所有真正的工作都是在代码中完成。如果图表就是代码，那么代码对图表的优势地位将被抹平。  
> Sometimes, a diagram can say more than a thousand lines of code. But, sadly, most of the time, software engineers give up on diagrams after the design phase, and all real work is done in code. The supremacy of code over diagrams would be leveled if diagrams were code.

在软件开发活动中，代码在被写出来之后，就拥有了相对其他任何知识媒介的巨大优势。不管是 UML 图、PRD，知识库还是口口相传，都在逐渐过时甚至被遗弃，只有代码在随着迭代不断有序更新和持续。  

**第二类误解是，认为 DDD 即便跟代码有关，代码的编写也是比较自由的，可以选择不同的架构模式、编程语言和代码风格。**

尽管可以在不同编程语言下实现 DDD ，但它们都需要满足——代码必须反映领域知识——这个要求。DDD 代码并不是随意编写的。

传统的 OOP 语言的 DDD 代码实践，并不能很好地达到用代码反映领域知识的目标。在这方面，**函数式语言（FP）大放异彩**。

参考[《用DDD(领域驱动设计)和ADT(代数数据类型)提升代码质量》](https://zhuanlan.zhihu.com/p/475789952)

**第三类误解是，认为 DDD 即便跟代码有关，也主要是后端代码，跟前端没什么关系。**

其实 DDD 跟代码在哪里运行无关，跟业务逻辑有关。

当我们的业务逻辑，放在服务端完成，由后端工程师跟进编写，DDD 就发生在了后端。

当我们的业务逻辑，放在前端完成，由前端工程师跟进编写，DDD 就发生在了前端。

DDD 在前端和后端中，也不是互斥的。它们可以同时成立，只要它们都承担着足够的业务逻辑。

**第四类误解是，DDD 是 CTO 和架构师的工作，跟普通开发者无关**

其实 DDD 可以分为两类：

-   狭义 DDD，围绕企业盈利逻辑的软件需求  
-   广义 DDD，围绕我们关心的特定领域问题

许多开发者所理解的 DDD 是狭义的，这是因为他们阅读的大部分 DDD 书籍，都是以企业的软件需求为主要案例。

这就进入了广义 DDD 的范畴。DDD 不只跟企业里的 CTO 和架构师有关系，跟每一位软件工程师都有关系。在宏观和微观的各个 Scope 里，DDD 都可以发挥作用。

DDD 的核心是——领域知识和代码逻辑的同构；服务于让代码反映真实的领域需求，从而提高交付的软件质量。它并未限定其它条件。

在业务领域，开发团队和领域专家往往是两拨人；然而在技术领域，开发团队同时就是该领域的专家本身，因此不容易被看到 DDD 战略设计中团队协作的环节，但不意味着 DDD 不存在。

**小结**

DDD 是一种端到端全链路考量软件设计的模式，致力于在每一个关键环节提升质量、降低复杂度。

-   DDD 有两个阶段：战略设计和战术设计。  
-   DDD 战略设计的核心是通过有效的团队协作，划分边界上下文（Bounded-Context），构建团队通用语言（Ubiquitous Language）。  
-   DDD 战略设计为其战术设计部分提供了可靠的领域知识/业务模型。  
-   DDD 战术设计的理论依据是——柯里-霍华德同构(Curry–Howard isomorphism)，它提供了用类型代码表达领域知识的方法。  
-   DDD 分为狭义和广义两种，广义 DDD 可普惠软件工程的所有层面，不局限于系统架构和商业模型等宏观层次。


## 参考资料

1.《用DDD(领域驱动设计)和ADT(代数数据类型)提升代码质量》： https://zhuanlan.zhihu.com/p/567512527  
2. Evans, Eric (2004). Domain-Driven Design: Tackling Complexity in the Heart of Software. Boston: Addison-Wesley. ISBN 978-032-112521-7. Retrieved 2012-08-12.
3. _Wikipedia contributors. "Domain-driven design." Wikipedia, The Free Encyclopedia. Wikipedia, The Free Encyclopedia, 31 Aug. 2022. Web. 7 Sep. 2022._
