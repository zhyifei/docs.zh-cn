---
title: "Seedwork （可重用基类，这些类和接口，您的域模型）"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Seedwork （可重用基类，这些类和接口，您的域模型）"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork （可重用基类，这些类和接口，您的域模型）

解决方案文件夹包含*SeedWork*文件夹。 *SeedWork*文件夹包含可以用作基础域实体和值对象的自定义基类。 使用这些基类的类，因此你不需要在每个域的对象类冗余代码。 此文件夹为这些类型的类称为*SeedWork*和不类似于*Framework*。 它称为*SeedWork*因为该文件夹包含仅的可重用的类不能真正将其视为一个框架的一小部分。 *Seedwork*由此引入一个术语[Michael 羽化](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826)和普遍通过[Martin Fowler](https://martinfowler.com/bliki/Seedwork.html)但你还可将该文件夹、 常用 SharedKernel，或类似。

图 9-12 显示排序的微服务中的窗体的域模型 seedwork 的类。 它还具有几个自定义的基本类，如实体、 ValueObject 和枚举，加上的几个接口。 （IRepository 和 IUnitOfWork） 这些接口需要实现有关通知基础结构层。 这些接口还使用通过依赖关系注入从应用程序层。

![](./media/image13.PNG)

**图 9-12**。 示例设置的域模型"seedwork"基本类和接口

这是许多开发人员共享项目，不正式 framework 之间的复制和粘贴重用的类型。 你可以在任何层或库中的 seedworks。 但是，如果组类和接口获取到足够大，你可能想要创建一个单个的类库。

## <a name="the-custom-entity-base-class"></a>自定义实体基类

下面的代码是实体基本类的一个示例可以由任何域实体，如实体 ID 相同的方式使用代码的放置位置[相等运算符](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)，等等。

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }
  
    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>域模型层中的存储库协定 （接口）

存储库协定都是只需.NET express 的存储库的协定要求对于每个聚合中使用的接口。 必须在域模型中; 实现的存储库本身，与 EF 核心代码或任何其他基础结构依赖关系和代码，存储库应仅实现你定义的接口。

这种做法 （在域模型层中放置存储库接口） 相关的模式是分隔接口模式。 作为[所述](http://www.martinfowler.com/eaaCatalog/separatedInterface.html)Martin Fowler 通过"使用分隔接口接口定义为在一个包，但在另一个中实现它。 这种方式可以客户端所需的依赖关系的接口的实现完全不能识别。"

执行分隔接口模式启用应用程序层 （在此情况下，微服务的 Web API 项目） 能够依赖于在域模型中，定义的要求，但不是直接依赖到基础结构/持久性层。 此外，你可以使用依赖关系注入隔离实现，它可以实现基础结构中持久性层使用存储库。

例如，下面的示例使用 IOrderRepository 界面定义 OrderRepository 类将需要在基础结构层实现的操作。 在应用程序的当前实现中，代码只需要将顺序添加到数据库，由于查询拆分以下未实现 CQS 方法和订单的更新。

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>其他资源

-   **Martin Fowler。分隔的接口。** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)


>[!div class="step-by-step"]
[以前](net-核心-微服务构成的域-model.md) [下一步] (实现值 objects.md)
