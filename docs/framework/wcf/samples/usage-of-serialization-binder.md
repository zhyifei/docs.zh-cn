---
title: 序列化联编程序的用法
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 5fd90febac8c75df9fa2472e4aab591a5630076e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33503153"
---
# <a name="usage-of-serialization-binder"></a>序列化联编程序的用法
此示例演示如何使用 <xref:System.Runtime.Serialization.SerializationBinder> 在序列化泛型类型时更改其版本。  
  
## <a name="demonstrates"></a>演示  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>讨论  
 此示例演示两个面向不同 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 版本的实体如何使用二进制格式化程序和序列化联编程序进行通信。  
  
 此示例的开发已使用 .NET 远程处理完成。 该示例包含一个面向 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 且使用泛型类型实现协定的服务器，以及两个不同的客户端（一个面向 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]，另一个面向 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]）。  
  
 服务器将一个 <xref:System.Runtime.Serialization.SerializationBinder> 附加到二进制格式化程序，以便在序列化时相应地更改类型版本，从而使两个客户端都可以正确反序列化这些类型。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  若要执行客户端，请右击解决方案 SBGenericsVTS （6 个项目），然后选择**属性**。  
  
2.  在**通用属性**，选择**启动项目**，然后选择**多启动项目**。  
  
3.  选择**服务器**第一个，然后**Client20**然后**Client40**。 选择**启动**操作为这三个项目，并将其余设置为保留**无**。  
  
4.  单击**确定**，然后按 F5 运行示例。
