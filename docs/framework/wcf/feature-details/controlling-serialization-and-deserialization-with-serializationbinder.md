---
title: 使用 SerializationBinder 控制序列化和反序列化
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41308de617fc02471ac2cb9769ec6e90e665e0b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="5c16b-102">使用 SerializationBinder 控制序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="5c16b-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="5c16b-103">在序列化过程中，格式化程序传输创建正确类型和版本的对象实例时所需的信息。</span><span class="sxs-lookup"><span data-stu-id="5c16b-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="5c16b-104">此信息通常包括对象的完整类型名称和程序集名称。</span><span class="sxs-lookup"><span data-stu-id="5c16b-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="5c16b-105">默认情况下，反序列化可使用此信息创建相同对象的实例。</span><span class="sxs-lookup"><span data-stu-id="5c16b-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="5c16b-106">由于原始类可能在执行反序列化的计算机上不存在，原始类已在程序集之间移动，或者服务器和客户端要求使用不同的类版本，因此有些用户可能需要控制要序列化和反序列化哪个类。</span><span class="sxs-lookup"><span data-stu-id="5c16b-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> <span data-ttu-id="5c16b-107">有关详细信息，请参阅[用法的序列化联编程序](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)。</span><span class="sxs-lookup"><span data-stu-id="5c16b-107">For more information, see [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5c16b-108">此功能仅在使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 或 <xref:System.Runtime.Serialization.NetDataContractSerializer> 时可用。</span><span class="sxs-lookup"><span data-stu-id="5c16b-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="5c16b-109">使用 SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="5c16b-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="5c16b-110"><xref:System.Runtime.Serialization.SerializationBinder> 是抽象类，用于控制在序列化和反序列化期间使用的实际类型。</span><span class="sxs-lookup"><span data-stu-id="5c16b-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="5c16b-111">若要控制在序列化和反序列化期间使用的类型，请从 <xref:System.Runtime.Serialization.SerializationBinder> 派生一个类，并重写 <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 和 <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 方法。</span><span class="sxs-lookup"><span data-stu-id="5c16b-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="5c16b-112"><xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> 方法采用 <xref:System.Type>，并返回程序集名称和类型名称。</span><span class="sxs-lookup"><span data-stu-id="5c16b-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="5c16b-113"><xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> 方法采用程序集名称和类型名称，并返回 <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="5c16b-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c16b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c16b-114">See Also</span></span>  
 [<span data-ttu-id="5c16b-115">序列化和反序列化</span><span class="sxs-lookup"><span data-stu-id="5c16b-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="5c16b-116">序列化活页夹的用法</span><span class="sxs-lookup"><span data-stu-id="5c16b-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
