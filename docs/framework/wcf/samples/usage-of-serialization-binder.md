---
title: 序列化联编程序的用法
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348458"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="ada72-102">序列化联编程序的用法</span><span class="sxs-lookup"><span data-stu-id="ada72-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="ada72-103">此示例演示如何使用 <xref:System.Runtime.Serialization.SerializationBinder> 在序列化泛型类型时更改其版本。</span><span class="sxs-lookup"><span data-stu-id="ada72-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ada72-104">演示</span><span class="sxs-lookup"><span data-stu-id="ada72-104">Demonstrates</span></span>  
 <span data-ttu-id="ada72-105"><xref:System.Runtime.Serialization.SerializationBinder>， <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="ada72-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ada72-106">讨论</span><span class="sxs-lookup"><span data-stu-id="ada72-106">Discussion</span></span>  
 <span data-ttu-id="ada72-107">此示例演示了两个实体，是面向不同版本的.NET Framework 可以通信中使用二进制格式化程序和序列化联编程序。</span><span class="sxs-lookup"><span data-stu-id="ada72-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="ada72-108">此示例被开发使用.NET 远程处理。</span><span class="sxs-lookup"><span data-stu-id="ada72-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="ada72-109">它包含的服务器目标[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]，它可实现的协定的泛型类型，和两个不同的客户端、 一个目标.NET Framework 2.0 和另一个面向[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ada72-109">It consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="ada72-110">服务器将一个 <xref:System.Runtime.Serialization.SerializationBinder> 附加到二进制格式化程序，以便在序列化时相应地更改类型版本，从而使两个客户端都可以正确反序列化这些类型。</span><span class="sxs-lookup"><span data-stu-id="ada72-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ada72-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="ada72-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="ada72-112">若要执行客户端，请右键单击解决方案，SBGenericsVTS （6 项目），然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ada72-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="ada72-113">在中**常见属性**，选择**启动项目**，然后选择**多个启动项目**。</span><span class="sxs-lookup"><span data-stu-id="ada72-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="ada72-114">选择**服务器**第一个，然后**Client20** ，然后**Client40**。</span><span class="sxs-lookup"><span data-stu-id="ada72-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="ada72-115">选择**启动**为这三个操作项目，并将设置为其余设置保留**None**。</span><span class="sxs-lookup"><span data-stu-id="ada72-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="ada72-116">单击**确定**，然后按 F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="ada72-116">Click **OK** and then press F5 to run the sample.</span></span>
