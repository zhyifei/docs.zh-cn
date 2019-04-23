---
title: 序列化联编程序的用法
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 47a1974386927316ea9230ec27cf647d7245c44a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329838"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="024ba-102">序列化联编程序的用法</span><span class="sxs-lookup"><span data-stu-id="024ba-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="024ba-103">此示例演示如何使用 <xref:System.Runtime.Serialization.SerializationBinder> 在序列化泛型类型时更改其版本。</span><span class="sxs-lookup"><span data-stu-id="024ba-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="024ba-104">演示</span><span class="sxs-lookup"><span data-stu-id="024ba-104">Demonstrates</span></span>  
 <span data-ttu-id="024ba-105"><xref:System.Runtime.Serialization.SerializationBinder>， <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="024ba-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="024ba-106">讨论</span><span class="sxs-lookup"><span data-stu-id="024ba-106">Discussion</span></span>  
 <span data-ttu-id="024ba-107">此示例演示两个面向不同 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 版本的实体如何使用二进制格式化程序和序列化联编程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="024ba-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="024ba-108">此示例的开发已使用 .NET 远程处理完成。</span><span class="sxs-lookup"><span data-stu-id="024ba-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="024ba-109">该示例包含一个面向 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 且使用泛型类型实现协定的服务器，以及两个不同的客户端（一个面向 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]，另一个面向 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]）。</span><span class="sxs-lookup"><span data-stu-id="024ba-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="024ba-110">服务器将一个 <xref:System.Runtime.Serialization.SerializationBinder> 附加到二进制格式化程序，以便在序列化时相应地更改类型版本，从而使两个客户端都可以正确反序列化这些类型。</span><span class="sxs-lookup"><span data-stu-id="024ba-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="024ba-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="024ba-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="024ba-112">若要执行客户端，请右键单击解决方案，SBGenericsVTS （6 项目），然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="024ba-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="024ba-113">在中**常见属性**，选择**启动项目**，然后选择**多个启动项目**。</span><span class="sxs-lookup"><span data-stu-id="024ba-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="024ba-114">选择**服务器**第一个，然后**Client20** ，然后**Client40**。</span><span class="sxs-lookup"><span data-stu-id="024ba-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="024ba-115">选择**启动**为这三个操作项目，并将设置为其余设置保留**None**。</span><span class="sxs-lookup"><span data-stu-id="024ba-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="024ba-116">单击**确定**，然后按 F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="024ba-116">Click **OK** and then press F5 to run the sample.</span></span>
