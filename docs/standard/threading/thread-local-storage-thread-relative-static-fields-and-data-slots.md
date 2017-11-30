---
title: "线程本地存储区：线程相关的静态字段和数据槽"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>线程本地存储区：线程相关的静态字段和数据槽
你可以使用托管的线程本地存储 (TLS) 来存储数据的独有线程和应用程序域。 .NET Framework 提供了两种方式使用托管 TLS： 线程相关的静态字段和数据槽。  
  
-   使用线程相关的静态字段 (与线程相关`Shared`在 Visual Basic 中的字段) 如果您可以预料到你在编译时的确切需求。 线程相关的静态字段提供最佳性能。 它们还会为你提供编译时类型检查的优点。  
  
-   当你实际要求可能会发现仅在运行时，请使用数据槽。 数据槽速度较慢且更难以使用比线程相关的静态字段，并且数据存储类型为<xref:System.Object>，因此您必须在使用它之前将它转换为正确的类型。  
  
 在非托管 c + + 中，你使用`TlsAlloc`来动态分配槽和`__declspec(thread)`来声明，应在线程相关的存储区中分配变量。 线程相关的静态字段和数据槽提供此行为的托管的版本。  
  
 在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>类，以创建第一次使用该对象时延迟初始化的线程本地对象。 若要了解详细信息，请参阅[迟缓初始化](../../../docs/framework/performance/lazy-initialization.md)  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>托管 TLS 中的数据的唯一性  
 无论使用线程相关的静态字段或数据槽的托管 TLS 中的数据是唯一的线程和应用程序域的组合。  
  
-   在应用程序域中，一个线程时，无法修改数据从另一个线程，即使这两个线程使用的相同字段或槽。  
  
-   当一个线程访问多个应用程序域中的相同字段或槽时，每个应用程序域中保留一个单独的值。  
  
 例如，如果某个线程设置的值与线程相关的静态字段，进入另一个应用程序域，，然后检索字段的值，第二个应用程序域中检索到的值不同于第一个应用程序域中的值。 在第二个应用程序域中设置字段的新值并不影响第一个应用程序域中的字段的值。  
  
 同样，当某个线程获取两个不同的应用程序域中的相同命名的数据槽，第一个应用程序域中的数据保留独立的第二个应用程序域中的数据。  
  
## <a name="thread-relative-static-fields"></a>线程相关的静态字段  
 如果你知道一段数据始终是唯一的线程和应用程序域组合，应用<xref:System.ThreadStaticAttribute>属性的静态字段。 像使用任何其他静态字段，请使用字段。 字段中的数据是唯一的使用它的每个线程。  
  
 线程相关的静态字段提供更好的性能比数据槽，并且具有编译时类型检查的好处。  
  
 请注意类构造函数的任何代码将访问该字段的第一个上下文中的第一个线程上运行。 在所有其他线程或上下文相同的应用程序域中，字段将初始化为`null`(`Nothing`在 Visual Basic 中) 如果它们是引用类型，或为其默认值，如果它们是值类型。 因此，你不应依赖于类的构造函数初始化线程相关的静态字段。 相反，避免初始化线程相关的静态字段和认为它们将初始化为`null`(`Nothing`) 或为其默认值。  
  
## <a name="data-slots"></a>数据槽  
 .NET Framework 提供了对线程和应用程序域的组合是唯一的动态数据槽。 有两种类型的数据槽： 名为槽和未命名的槽。 通过使用实现了同时<xref:System.LocalDataStoreSlot>结构。  
  
-   若要创建命名的数据槽，请使用<xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType>或<xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>方法。 若要获取对现有的已命名的槽的引用，其将名称传递给<xref:System.Threading.Thread.GetNamedDataSlot%2A>方法。  
  
-   若要创建未命名的数据槽，请使用<xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>方法。  
  
 对于名为和未命名的槽，则使用<xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType>和<xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType>方法用于设置和检索的槽中的信息。 这些是始终作用于的线程的当前正在执行它们的数据的静态方法。  
  
 命名的槽可以很方便，因为你可以通过其将名称传递给需要检索槽<xref:System.Threading.Thread.GetNamedDataSlot%2A>方法，而不是维护对未命名的槽的引用。 但是，如果另一个组件使用其线程相关的存储区的相同名称和线程执行你的组件和其他组件中的代码，这两个组件可能会破坏彼此的数据。 （此方案假设这两个组件正在运行在相同的应用程序域中，和，它们不设计共享相同的数据）。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [线程处理](../../../docs/standard/threading/index.md)
