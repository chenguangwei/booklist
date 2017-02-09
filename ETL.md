ETL，是英文 Extract-Transform-Load 的缩写，用来描述将数据从来源端经过抽取（extract）、转换（transform）、加载（load）至目的端的过程。ETL 是构建数据仓库的重要一环，用户从数据源抽取出所需的数据，经过数据清洗，最终按照预先定义好的数据仓库模型，将数据加载到数据仓库中去。

我们在下方列出了 7 款开源的 ETL 工具，并讨论了从 ETL 转向“无 ETL”的过程，因为 ELT 正迅速成为现代数据和云环境的终极过程。

注：原文包含 11 项 ETL 工具，本文提取了其中开源的 7 项，如需对另外 4 项进行了解，可点击文末链接进行查看。

优秀的 ETL 工具

1、Apache Camel

Apache Camel 是一个非常强大的基于规则的路由以及媒介引擎，该引擎提供了一个基于 POJO 的企业应用模式（Enterprise Integration Patterns）的实现，你可以采用其异常强大且十分易用的 API （可以说是一种 Java 的领域定义语言 Domain Specific Language）来配置其路由或者中介的规则。 通过这种领域定义语言，你可以在你的 IDE 中用简单的 Java Code 就可以写出一个类型安全并具有一定智能的规则描述文件。



主页：http://camel.apache.org/

2、Apache Kafka

Apache Kafka 是一个开源的消息系统，用 Scale 和 Java 写成。该项目为处理实时数据提供了一个统一、高通量、低延时的平台。有如下特性：

通过 O(1) 的磁盘数据结构提供消息的持久化，这种结构对于即使数以TB的消息存储也能够保持长时间的稳定性能。

高吞吐量：即使是非常普通的硬件 kafka 也可以支持每秒数十万的消息。

支持通过 kafka 服务器和消费机集群来分区消息。

支持 Hadoop 并行数据加载。

主页：https://kafka.apache.org/

3、Apatar

Apatar 用 Java 编写，是一个开源的数据抽取、转换、 装载（ETL）项目。模块化的架构。提供可视化的 Job 设计器与映射工具，支持所有主流数据源，提供灵活的基于 GUI、服务器和嵌入式的部署选项。它具有符合 Unicode 的功能，可用于跨团队集成数据，填充数据仓库与数据市场，在连接到其他系统时在代码少量或没有代码的情况下进行维护。

主页：http://apatar.com/

4、Heka

来自 Mozilla 的 Heka 是一个用来收集和整理来自多个不同源的数据的工具，通过对数据进行收集和整理后发送结果报告到不同的目标用于进一步分析。



主页：http://hekad.readthedocs.io/en/v0.10.0/

5、Logstash

Logstash 是一个应用程序日志、事件的传输、处理、管理和搜索的平台。你可以用它来统一对应用程序日志进行收集管理，提供 Web 接口用于查询和统计。Logstash 现在是 ElasticSearch 家族成员之一。

主页：https://www.elastic.co/products/logstash

6、Scriptella

Scriptella 是一个开源的 ETL （抽取-转换-加载）工具和一个脚本执行工具，采用 Java 开发。Scriptella 支持跨数据库的 ETL 脚本，并且可以在单个的 ETL 文件中与多个数据源运行。Scriptella 可与任何 JDBC / ODBC 兼容的驱动程序集成，并提供与非 JDBC 数据源和脚本语言的互操作性的接口。它还可以与 Java EE，Spring，JMX，JNDI 和 JavaMail 集成。



主页：http://scriptella.org/

7、Talend

Talend (踏蓝) 是第一家针对的数据集成工具市场的 ETL（数据的提取 Extract、传输 Transform、载入Load）开源软件供应商。Talend 以它的技术和商业双重模式为 ETL 服务提供了一个全新的远景。它打破了传统的独有封闭服务，提供了一个针对所有规模的公司的公开的，创新的，强大的灵活的软件解决方案。最终，由于 Talend 的出现，数据整合方案不再被大公司所独享。

主页：http://www.talend.com/

8、kettle
Kettle是一款国外开源的ETL工具，纯java编写，可以在Window、Linux、Unix上运行，数据抽取高效稳定。

Kettle 中文名称叫水壶，该项目的主程序员MATT 希望把各种数据放到一个壶里，然后以一种指定的格式流出。

Kettle中有两种脚本文件，transformation和job，transformation完成针对数据的基础转换，job则完成整个工作流的控制。

ELT 初探

虽然 Stitch 也是一个 ETL 服务企业，但其 CEO 在 TechTarget 杂志的访谈中也称赞了 AWS Athena 服务，同时提出了从 ETL 转向 ELT 的需要。

在他看来，“无 ETL”即 ETL 过程由提取（Extract），加载（Load），变换（Transform）代替，其中数据变换根据下游使用的需要而在 SQL 中进行，而不是在加载阶段期间。他承认 ETL 公司来推广 ELT 概念有点让人匪夷所思，但他解释了这么做的好处。

“使用 Athena，你可以从数据源中提取数据，经过少量或不加载预处理后进行加载。 这种风格的 ELT 是大多数使用案例的优秀模型，因为它能产生更简单的架构，使分析人员更好地了解原始数据的变换过程。”点此了解更多。

使用 ELT 方法，在提取完成之后，数据加载会立即开始，而不用等待“恰当的”数据变换操作。 转换还可以在查询时运行，比 ETL 更省时，因为 ETL 需要用户等待转换完成。 ELT 允许 BI 用户和分析人员无限制地访问整个原始数据，为用户提供了更大的灵活性，使之能更好地支持该业务。