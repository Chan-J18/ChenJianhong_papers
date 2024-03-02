
# List

### Hybrid Fuzzer
<!-- 已阅读-->
[Fuzzy-Sat：Fuzzing Symbolic Expressions](https://arxiv.org/pdf/2102.06580.pdf)<br> 
<!-- 已阅读-->
[FUZZOLIC: mixing fuzzing and concolic execution](https://www.researchgate.net/publication/352346470_FUZZOLIC_mixing_fuzzing_and_concolic_execution)<br>
<!-- 已阅读-->
[Qsym : A Practical Concolic Execution Engine Tailored for Hybrid Fuzzing](https://www.usenix.org/system/files/conference/usenixsecurity18/sec18-yun.pdf)<br>

[Grey-Box Concolic Testing on Binary Code](https://softsec.kaist.ac.kr/~sangkilc/papers/choi-icse2019.pdf)<br>


### Coverage guided fuzzing（CGF）
<!-- 已阅读-->
[REDQUEEN: Fuzzing with Input-to-State Correspondence](https://wcventure.github.io/FuzzingPaper/Paper/NDSS19_REDQUEEN.pdf)

### Symbolic Executor
[EXE: Automatically Generating Inputs of Death]()<br>
<!-- 已阅读-->
[KLEE: Unassisted and Automatic Generation of High-Coverage Tests for Complex Systems Programs](https://www.usenix.org/legacy/event/osdi08/tech/full_papers/cadar/cadar.pdf)<br>

### Concolic Testing
<!-- 已阅读-->
[Symbolic execution with SYMCC: Don’t interpret, compile!](https://www.usenix.org/system/files/sec20-poeplau.pdf)<br>
<!-- 已阅读-->
[SymQEMU: Compilation-based symbolic execution for binaries](https://www.s3.eurecom.fr/docs/ndss21_symqemu.pdf)<br>


### Rust Testing
[RULF: Rust Library Fuzzing via API Dependency Graph Traversal](https://arxiv.org/pdf/2104.12064.pdf) <br>
[SymRustC: A Hybrid Fuzzer for Rust](https://dl.acm.org/doi/epdf/10.1145/3597926.3604927)<br>


---

# Papers
### Hybrid Fuzzer
- **Name**   <br>
**摘要：**   <br>
**关键词：**  <br>

- **Fuzzy-Sat：Fuzzing Symbolic Expressions**<br>
**摘要：** 研究了是否可以应用从fuzzing领域借用的技术来检查符号约束在concolic背景下是否可满足，从而为经典 SMT 求解技术提供了可行的替代方案。设计了一种新的近似求解器 FUZZY-SAT，并表明在处理hybrid fuzzer生成的查询方面，能与 Z3 等最先进的求解器既具有竞争性又具有互补性<br>
**关键词：** Concolic execution、Fuzzing testing、SMT Solver、Hybrid fuzzing<br>
**基本思想：** 利用fuzzing方面的一些技术来设计实现了一个近似求解器的Fuzzy-Sat，以准确性为代价换来SMT solver的可扩展性和高效性。<br>


- **FUZZOLIC: mixing fuzzing and concolic execution**   <br>
**摘要：**   设计了一种新颖的 concolic 执行器，它可以在 QEMU 下运行时分析复杂的二进制程序，并有效地生成符号查询，在解决时可以生成有价值的程序输入。<br>
**关键词：**  Concolic execution、Fuzzing testing、SMT Solver、Hybrid fuzzing<br>
**基本思想：** 提出了一种新颖的 concolic 框架，称为 Fuzzolic，它构建在二进制翻译器 QEMU 之上。用上面的Fuzzy-Sat求解得到的符号表达式。<br>

- **QSYM** <br>
**摘要：** 并行执行AFL和Concolic Testing，允许两个测试组件之间共享他们的输入队列 <br>
**关键词：** Hybrid Fuzzer、Parallel<br>

- **Grey-Box Concolic Testing on Binary Code**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>


- **DRILLER** <br>
**摘要：** 交替使用AFL和ANGR，当AFL在一段特定时间无法产生新的interesting输入，则转换为ANGR进行测试。<br>
**关键词：** Hybrid Fuzzer、Alternate<br>
...

***
### Coverage guided fuzzing(CGF)
- **Name**<br>
**摘要：** <br>
**关键词：** <br>

- **REDQUEEN: Fuzzing with Input-to-State Correspondence**  <br>
  **摘要:** 基于覆盖率引导的模糊测试器AFL，仍存在两个常见问题：魔数Magic bytes和（嵌套）校验和Checksums。为了克服这些障碍，通常会使用计算昂贵的方法，如污点跟踪和符号执行。缺点是通常需要访问源代码，对环境（如库调用行为或底层操作系统）需要相当精确的描述建模，或是需要平台指令集的准确语义。论文提出了一种轻量级但非常有效的方法来替代污点跟踪和符号执行，并且能够轻松扩展到大型二进制应用程序和未知环境。
  在给定程序的执行过程中，输入的部分内容往往会直接（即几乎未经修改）进入程序状态。利用这种输入到状态的对应关系，以高效的方式克服常见的模糊测试障碍。 论文实现了名为 REDQUEEN，能够自动解决给定二进制可执行文件的神奇字节和（嵌套）校验和测试。<br>
  **关键词：** Checksums、Magic Bytes、a strong input-to-state correspondence、DTA、CGF   <br>

- **Coverage-based Greybox Fuzzing as Markov Chain**<br>
  **摘要:**<br>
  **关键词：**<br>

  - **LAF-INTEL**<br>
**摘要：** 将多字节检查拆分为单字节比较，帮助模糊器在推理分支条件时跟踪中间进度  <br>
**关键词：** 多字节拆分、CGF<br>

- **VUZZER**<br>
**摘要：** 将动态污点分析（DTA）集成到模糊器中，识别哪些字节会影响分支条件中的操作数，从而绕过对Magic Bytes的检查<br>
**关键词：** Magic Bytes、CGF、DTA<br>

- **ANGORA**<br>
**摘要：** 通过执行多字节动态污点分析（DTA）和使用梯度下降来有效地改变污点输入字节<br>
**关键词：** 多字节、DTA、Gradient Descent<br>
  
- **WEIZZ**<br>
**摘要：** 通过每次翻转输入中的一个位bit，在每次位翻转后检查哪些比较操作数在程序执行过程中发生了变化，从而可能表明改变的位与受影响的分支条件之间存在依赖关系。<br>
**关键词：** CGF、位与分支条件的依赖关系<br>  
  
  - **SLF**<br>
**摘要：** 利用类似与WEIZZ的位翻转策略，为应用程序生成有效输入，即使最初没有有意义的种。借助输入依赖性分析，SLF可以识别输入中的字段，然后采用基于梯度的多目标搜索启发式来处理程序中相互依赖检查<br>
**关键词：** CGF、位与分支条件的依赖关系<br>

- **ECLIPSER**<br>
**摘要：** <br>
**关键词：** <br>
**基本思想：** <br>
...
***
### Symbolic Executor
- **Name**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>

- **KLEE**<br>
**摘要：** 基于传统符号执行的思想，基于LLVM实现的对待测程序的LLVM bitcode进行解释执行并进行符号化过程的符号执行器。<br>
**关键词：** Symbolic Executor、LLVM、SMT Solver<br>
**基本思想：** 解释执行编译为LLVM bitcode的待测程序，并在解释执行的过程中，进行符号表达式生成，并且实现了环境的模拟，和一些查询优化，每一个符号化过程为一个state，有state相关的调度等。<br>

- **EXE**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>


....

***

### Concolic Testing
- **Name**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>



- **Name**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>

...

***
### Rust Testing
- **Name**<br>
**摘要：**<br>
**关键词：**<br>
**基本思想：** <br>

- **Name**<br>
**摘要：**<br>
**关键词：**<br>

- **Name**<br>
**摘要：**<br>
**关键词：**<br>
  