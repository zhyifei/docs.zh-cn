---
title: 序列化联编程序的用法
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138649"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="5444a-102">序列化联编程序的用法</span><span class="sxs-lookup"><span data-stu-id="5444a-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="5444a-103">此示例演示如何使用 <xref:System.Runtime.Serialization.SerializationBinder> 在序列化泛型类型时更改其版本。</span><span class="sxs-lookup"><span data-stu-id="5444a-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5444a-104">演示</span><span class="sxs-lookup"><span data-stu-id="5444a-104">Demonstrates</span></span>  
 <span data-ttu-id="5444a-105"><xref:System.Runtime.Serialization.SerializationBinder>，<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="5444a-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5444a-106">讨论</span><span class="sxs-lookup"><span data-stu-id="5444a-106">Discussion</span></span>  
 <span data-ttu-id="5444a-107">此示例显示面向不同版本的 .NET Framework 的两个实体如何使用二进制格式化程序和序列化联编程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="5444a-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="5444a-108">此示例是使用 .NET 远程处理开发的。</span><span class="sxs-lookup"><span data-stu-id="5444a-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="5444a-109">它包含目标为 .NET Framework 4 的服务器，该服务器可实现一个具有泛型类型的协定，以及两个不同的客户端，一个目标 .NET Framework 2.0，另一个目标 .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="5444a-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="5444a-110">服务器将一个 <xref:System.Runtime.Serialization.SerializationBinder> 附加到二进制格式化程序，以便在序列化时相应地更改类型版本，从而使两个客户端都可以正确反序列化这些类型。</span><span class="sxs-lookup"><span data-stu-id="5444a-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5444a-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="5444a-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="5444a-112">若要执行该客户端，请右键单击解决方案 SBGenericsVTS （6个项目），然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="5444a-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="5444a-113">在 "**通用属性**" 中，选择 "**启动项目**"，然后选择 "**多启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="5444a-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="5444a-114">依次选择 " **Server** "、" **Client20** " 和 " **Client40**"。</span><span class="sxs-lookup"><span data-stu-id="5444a-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="5444a-115">选择这三个项目的 "**启动**" 操作，并将 rest 设置为 "**无**"。</span><span class="sxs-lookup"><span data-stu-id="5444a-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="5444a-116">单击 **"确定"** ，然后按 F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="5444a-116">Click **OK** and then press F5 to run the sample.</span></span>
