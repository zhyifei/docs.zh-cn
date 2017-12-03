---
title: "版本容错序列化回调"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70b89ff741d2a2036d5684ebc4526a6cb7ec49d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="fa549-102">版本容错序列化回调</span><span class="sxs-lookup"><span data-stu-id="fa549-102">Version-Tolerant Serialization Callbacks</span></span>
<span data-ttu-id="fa549-103">数据协定编程模型充分支持 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 和 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 类所支持的版本容错序列化回调方法。</span><span class="sxs-lookup"><span data-stu-id="fa549-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="fa549-104">版本容错属性</span><span class="sxs-lookup"><span data-stu-id="fa549-104">Version-Tolerant Attributes</span></span>  
 <span data-ttu-id="fa549-105">共有四个回调属性。</span><span class="sxs-lookup"><span data-stu-id="fa549-105">There are four callback attributes.</span></span> <span data-ttu-id="fa549-106">每个属性都可应用于序列化/反序列化引擎在不同时间调用的方法。</span><span class="sxs-lookup"><span data-stu-id="fa549-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="fa549-107">下表说明使用每个属性的时间。</span><span class="sxs-lookup"><span data-stu-id="fa549-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="fa549-108">特性</span><span class="sxs-lookup"><span data-stu-id="fa549-108">Attribute</span></span>|<span data-ttu-id="fa549-109">调用相应方法时。</span><span class="sxs-lookup"><span data-stu-id="fa549-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="fa549-110">在序列化类型之前调用。</span><span class="sxs-lookup"><span data-stu-id="fa549-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="fa549-111">在序列化类型之后调用。</span><span class="sxs-lookup"><span data-stu-id="fa549-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="fa549-112">在反序列化类型之前调用。</span><span class="sxs-lookup"><span data-stu-id="fa549-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="fa549-113">在反序列化类型之后调用。</span><span class="sxs-lookup"><span data-stu-id="fa549-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="fa549-114">该方法必须接受 <xref:System.Runtime.Serialization.StreamingContext> 参数。</span><span class="sxs-lookup"><span data-stu-id="fa549-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="fa549-115">这些方法主要计划用于版本控制或初始化。</span><span class="sxs-lookup"><span data-stu-id="fa549-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="fa549-116">反序列化期间，不调用任何构造函数。</span><span class="sxs-lookup"><span data-stu-id="fa549-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="fa549-117">因此，如果传入流中缺少数据成员的数据，则这些成员可能不会正确初始化（为既定的默认值），例如，如果数据来自缺少某些数据成员的类型的上一版本。</span><span class="sxs-lookup"><span data-stu-id="fa549-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="fa549-118">若要更正此错误，请使用加有 <xref:System.Runtime.Serialization.OnDeserializingAttribute> 标记的回调方法，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="fa549-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fa549-119">只能使用上述每个回调属性对每个类型标记一个方法。</span><span class="sxs-lookup"><span data-stu-id="fa549-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fa549-120">示例</span><span class="sxs-lookup"><span data-stu-id="fa549-120">Example</span></span>  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="fa549-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa549-121">See Also</span></span>  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [<span data-ttu-id="fa549-122">版本容错序列化</span><span class="sxs-lookup"><span data-stu-id="fa549-122">Version Tolerant Serialization</span></span>](../../../../docs/standard/serialization/version-tolerant-serialization.md)
