---
title: 实体框架术语
ms.date: 03/30/2017
ms.assetid: fa2a1bd1-6118-487b-8673-eebc66b92945
ms.openlocfilehash: 9d3767e73ffe1d9ee5d363e36a0661cc0fb517d9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248245"
---
# <a name="entity-framework-terminology"></a>实体框架术语
本主题定义了文档中经常[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]引用的术语。 如果有其他可用信息，则会提供指向相关主题的链接。  
  
|术语|定义|  
|----------|----------------|  
|Association — 关联|实体类型之间的关系的定义。<br /><br /> 有关详细信息，请参阅[Association 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#association-element-csdl)和[关联类型](../association-type.md)。|  
|Association Set — 关联集|包含同一类型关联实例的逻辑容器。<br /><br /> 有关详细信息，请参阅[AssociationSet 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#associationset-element-csdl)和[关联集](../association-set.md)。|  
|Code First|从 实体框架4.1 开始，可使用 Code First 开发以编程方式创建模型。 对于 Code First 开发，有两种不同的方案。 在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。<br /><br /> 请注意，Code First 开发是[实体框架 5.0](https://go.microsoft.com/fwlink/?LinkId=234900)的组成部分。 Entity Framework 5.0 不是 .NET Framework 的一部分，但基于 .NET Framework 4.5 构建。 实体框架5.0 作为["实体框架"](https://go.microsoft.com/fwlink/?LinkID=215714)[NuGet](https://go.microsoft.com/fwlink/?LinkId=232488)包提供。 有关详细信息，请参阅[实体框架版本和版本控制](https://go.microsoft.com/fwlink/?LinkId=234899)。|  
|Command Tree — 命令目录树|由一个或多个表达式组成[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]的所有查询的常见编程表示形式。<br /><br /> 有关详细信息，请参阅[实体框架概述](overview.md)。|  
|Complex Type — 复杂类型|一种 .NET Framework 类，表示概念模型中定义的复杂属性。 通过复杂类型，可以在实体中组织标量属性。 复杂对象是复杂类型的实例。 有关详细信息，请参阅[ComplexType 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#complextype-element-csdl)和[复杂类型](../complex-type.md)。|  
|ComplexType|数据类型的规范，表示没有键属性的实体类型的非标量属性。<br /><br /> 有关详细信息，请参阅[ComplexType 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#complextype-element-csdl)和[复杂类型](../complex-type.md)。|  
|Conceptual Model — 概念模型|[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]的应用程序域中实体类型、复杂类型、关联、实体容器、实体集和关联集的抽象规范。 概念模型在 .csdl 文件中采用 CSDL 定义。<br /><br /> 有关详细信息，请参阅[建模和映射](modeling-and-mapping.md)。|  
|.csdl 文件|一种 XML 文件，该文件包含以 CSDL 表示的概念模型。|  
|概念性架构定义语言 (CSDL)|一种基于 XML 的语言，可用于定义概念模型的实体类型、关联、实体容器、实体集和关联集。<br /><br /> 有关详细信息，请参阅 [CSDL Specification](./language-reference/csdl-specification.md)。|  
|Container — 容器|实体集和关联集的逻辑分组。<br /><br /> 有关详细信息，请参阅[EntityContainer 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entitycontainer-element-csdl)和[实体容器](../entity-container.md)。|  
|并发|允许多个用户同时访问和更改共享数据的进程。 默认情况下，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]实现开放式并发模型。|  
|方向|指某些关联的非对称性。 方向是通过架构中的 `FromRole` 或 `ToRole` 元素的 `NavigationProperty` 和 `ReferentialConstraint` 属性指定的。<br /><br /> 有关详细信息，请参阅[NavigationProperty 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#navigationproperty-element-csdl)和[导航属性](../navigation-property.md)。|  
|Eager Loading — 预先加载|加载特定相关对象集以及在查询中显式请求的对象的过程。|  
|.edmx 文件|一种 XML 文件，该文件包含概念模型（以 CSDL 表示）、存储模型（以 SSDL 表示）以及这两个模型之间的映射（以 MSL 表示）。 该 .edmx 文件由实体数据模型工具创建。 有关详细信息，请参阅[.Edmx 文件概述](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))。|  
|end|参与关联的实体。<br /><br /> 有关详细信息，请参阅[结束元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#end-element-csdl)和[关联端](../association-end.md)。|  
|Entity — 实体|应用程序域中的概念，数据类型是根据实体定义的。<br /><br /> 有关详细信息，请参阅[EntityType 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entitytype-element-csdl)和[实体类型](../entity-type.md)。|  
|EntityClient|一个独立于存储的 ADO.NET 数据提供程序，其中包含`EntityConnection`类`EntityCommand`，如`EntityDataReader`、和。 使用[!INCLUDE[esql](../../../../../includes/esql-md.md)]并连接到存储特定的 ADO.NET 数据提供程序， `SqlClient`例如。<br /><br /> 有关详细信息，请参阅[实体框架的 EntityClient Provider](entityclient-provider-for-the-entity-framework.md)。|  
|Entity Container — 实体容器|用于指定将在指定的命名空间中实现的实体集和关联集。<br /><br /> 有关详细信息，请参阅[EntityContainer 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entitycontainer-element-csdl)和[实体容器](../entity-container.md)。|  
|实体数据模型 (EDM)|以实体和关系来描述数据结构（不考虑其存储形式）的一组概念。<br /><br /> 有关详细信息，请参阅[实体数据模型](../entity-data-model.md)。|  
|Entity Framework|一套支持开发面向数据的软件应用程序的技术，这些技术使开发人员能够处理映射到数据源中的逻辑架构的概念模型。<br /><br /> 有关详细信息，请参阅[实体框架概述](overview.md)。|  
|实体集|一种逻辑容器，包含给定类型及其子类型的实体。 实体集映射到数据库中的表。<br /><br /> 有关详细信息，请参阅[EntitySet 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entityset-element-csdl)和[实体集](../entity-set.md)。|  
|Entity SQL|一种与存储无关的 SQL 方言，它可直接处理概念实体架构，并支持概念模型概念（如继承和关系）。<br /><br /> 有关详细信息，请参阅[实体 SQL 语言](./language-reference/entity-sql-language.md)。|  
|Entity Type — 实体类型|一个 .NET Framework 类，该类表示在概念模型中定义的实体。 实体类型可以具有标量属性、复杂属性和导航属性。 对象是实体类型的实例。 有关详细信息，请参阅使用[对象](working-with-objects.md)。|  
|EntityType|数据类型的规范，它包含一个键和一个命名属性集，表示概念模型或存储模型中的顶级项。<br /><br /> 有关详细信息，请参阅[EntityType 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entitytype-element-csdl)和[实体类型](../entity-type.md)。|  
|Explicit Loading — 显式加载|当查询返回对象时，不会同时加载相关对象。 默认情况下，只有对导航属性使用 `Load` 方法显式请求时才会加载相关对象。|  
|外键关联|实体之间的关联，通过外键属性进行管理。|  
|标识关系|一种关系，其中主体实体的主键是依赖实体的主键的一部分。 在这种关系中，没有主体实体，依赖实体就不能存在。|  
|独立关联|实体之间的关联，由独立对象表示和跟踪。|  
|密钥|实体类型的属性 (Attribute)，用于指定使用哪个属性 (Property) 或属性 (Property) 集标识实体类型的唯一实例。 在对象层中由 <xref:System.Data.EntityKey> 类表示。<br /><br /> 有关详细信息，请参阅[Key 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#key-element-csdl)和[实体键](../entity-key.md)。|  
|延迟加载|当查询返回对象时，不会同时加载相关对象。 但在访问导航属性时，会自动加载相关对象。|  
|LINQ to Entities|一种查询语法，用于定义一组查询运算符，这些运算符允许遍历、筛选和投影操作以直接的声明性方式在 Visual C#和 Visual Basic 中表示。<br /><br /> 有关详细信息，请参阅[LINQ to Entities](./language-reference/linq-to-entities.md)。|  
|映射|概念模型与存储模型中的项之间的对应规范。<br /><br /> 有关详细信息，请参阅[MSL 规范](./language-reference/msl-specification.md)。|  
|.msl 文件|一种 XML 文件，该文件以 MSL 表示，包含概念模型与存储模型之间的映射。|  
|映射规范语言 (MSL)|一种基于 XML 的语言，可用于将概念模型中定义的项映射到存储模型中的项。<br /><br /> 有关详细信息，请参阅[MSL 规范](./language-reference/msl-specification.md)。|  
|Modification Functions — 修改函数|用于插入、更新和删除数据源中的数据的存储过程。 这类函数可用来替代[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]生成的命令。 修改函数是由存储模型中的 `Function` 元素定义的。 [ModificationFunctionMapping](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716778(v=vs.100))元素将这些修改函数映射到对概念模型中定义的实体的插入、更新和删除操作。|  
|重数|关系每一方可以存在的实体数量，由关联进行定义。 也称为基数。<br /><br /> 有关详细信息，请参阅[结束元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#end-element-csdl)和[关联端](../association-end.md)。|  
|Multiple Entity Sets Per Type — 每种类型多个实体集|在多个实体集中定义一个实体类型的功能。<br /><br /> 有关详细信息，请参阅[EntitySet 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#entityset-element-csdl)和[如何：为每个类型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738537(v=vs.100))定义一个具有多个实体集的模型。|  
|Navigation Property — 导航属性|实体类型的属性，表示与其他实体类型的关系，由关联定义。 导航属性用于根据关联另一端的重数返回相关对象，如 <xref:System.Data.Objects.DataClasses.EntityCollection%601> 或 <xref:System.Data.Objects.DataClasses.EntityReference%601>。<br /><br /> 有关详细信息，请参阅[NavigationProperty 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#navigationproperty-element-csdl)和[导航属性](../navigation-property.md)。|  
|Query Path — 查询路径|路径的字符串表示形式，用于指定执行对象查询时要返回的相关对象。 查询路径是通过调用 <xref:System.Data.Objects.ObjectQuery%601.Include%2A> 的 <xref:System.Data.Objects.ObjectQuery%601> 方法定义的。<br /><br /> 有关详细信息，请参阅[加载相关对象](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896272(v=vs.100))。|  
|对象上下文|表示概念模型中定义的实体容器。 它包含与基础数据源的连接，并提供更改跟踪和标识解析等服务。 对象上下文由 <xref:System.Data.Objects.ObjectContext> 或 `DbContext` 类的实例表示。<br /><br /> `DbContext`是[实体框架 5.0](https://go.microsoft.com/fwlink/?LinkId=234900)的一部分。 Entity Framework 5.0 不是 .NET Framework 的一部分，但基于 .NET Framework 4.5 构建。 实体框架5.0 作为["实体框架"](https://go.microsoft.com/fwlink/?LinkID=215714)[NuGet](https://go.microsoft.com/fwlink/?LinkId=232488)包提供。 有关详细信息，请参阅[实体框架版本和版本控制](https://go.microsoft.com/fwlink/?LinkId=234899)。|  
|对象层|实体框架所使用的实体类型和对象上下文定义。|  
|Object Query — 对象查询|在对象上下文中对数据模型执行的查询，该查询以对象形式返回数据。<br /><br /> 有关详细信息，请参阅[对象查询](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100))。|  
|Object-relational Mapping — 对象关系映射|一种技术，用于将关系数据库中的数据转换为可在面向对象的软件应用程序中使用的数据类型。<br /><br /> [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]通过将存储模型中定义的关系数据映射到概念模型中定义的数据类型来提供对象关系映射服务。<br /><br /> 有关详细信息，请参阅[建模和映射](modeling-and-mapping.md)。|  
|Object Services — 对象服务|提供的服务[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ，使应用程序代码能够对 .NET Framework 对象之类的实体进行操作。|  
|持久性未知对象|一种不包含与数据存储有关的任何逻辑的对象。 也称为 POCO 实体。|  
|POCO|纯旧式 CLR 对象。 一种不从另一个类继承也不实现接口的对象。|  
|POCO 实体|[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中的一种实体，该实体不从 <xref:System.Data.Objects.DataClasses.EntityObject> 或 <xref:System.Data.Objects.DataClasses.ComplexObject> 继承，也不实现[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]接口。 通常，POCO 实体是在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]应用程序中使用的现有域对象。 这些实体支持持久性未知。 有关详细信息，请参阅使用[POCO 实体](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100))。|  
|代理对象|一种从 POCO 类派生的对象，该对象由[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]生成，以支持更改跟踪和延迟加载。 有关详细信息，请参阅[创建 POCO 代理的要求](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd468057(v=vs.100))。|  
|Referential Constraint — 引用约束|在概念模型中定义的约束，该约束指示一个实体与另一个实体之间存在依赖关系。 此约束意味着，如果没有对应的主体实体实例，就不会存在依赖性实体的实例。<br /><br /> 有关详细信息，请参阅[ReferentialConstraint 元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#referentialconstraint-element-csdl)和[引用完整性约束](../referential-integrity-constraint.md)。|  
|Relationship — 关系|实体之间的逻辑连接。|  
|角色 (role)|为关联的每个 `End` 提供的名称，用于明确关系的语义。<br /><br /> 有关详细信息，请参阅[结束元素（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#end-element-csdl)和[关联端](../association-end.md)。|  
|标量属性|实体的属性，它映射到存储模型中的单个字段。|  
|自跟踪实体|从文本模板转换工具包 (T4) 中生成的一种实体，该实体可以将更改记录到标量属性、复杂属性以及导航属性中。|  
|Simple Type — 简单类型|一种基元类型，用于定义概念模型中的属性。<br /><br /> 有关详细信息，请参阅[概念模型类型（CSDL）](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)和[实体数据模型：基元数据类型](../entity-data-model-primitive-data-types.md)。|  
|Split Type — 拆分实体|一种实体类型，它映射到存储模型中的两个不同类型。<br /><br /> 有关详细信息，请参阅[如何：使用映射到两个表](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896233(v=vs.100))的单个实体定义模型。|  
|存储模型|受支持的数据源（例如关系数据库）的数据逻辑模型定义。 存储模型在 .ssdl 文件中采用 SSDL 定义。<br /><br /> 有关详细信息，请参阅[建模和映射](modeling-and-mapping.md)和[SSDL 规范](./language-reference/ssdl-specification.md)。|  
|.ssdl 文件|一种 XML 文件，该文件包含以 SSDL 表示的存储模型。|  
|存储架构定义语言 (SSDL)|一种基于 XML 的语言，用于定义存储模型（常常对应于数据库架构）的实体类型、关联、实体容器、实体集和关联集。<br /><br /> 有关详细信息，请参阅[SSDL 规范](./language-reference/ssdl-specification.md)。|  
|每个层次结构一个表|在数据库中对类型层次结构建模的方法，此方法将层次结构中的所有类型的特性包含在一个表中。|  
|每个类型一个表|在数据库中对类型层次结构建模的方法，此方法使用具有一对一关系的多个表来对各种类型建模。|  
  
## <a name="see-also"></a>请参阅

- [ADO.NET 实体框架](index.md)
- [实体框架概述](overview.md)
- [入门](getting-started.md)
- [实体框架资源](resources.md)
