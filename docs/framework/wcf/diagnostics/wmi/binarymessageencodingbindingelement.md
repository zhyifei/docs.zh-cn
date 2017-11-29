---
title: BinaryMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 09d43ed76ef70f4478aa1029c254a7b1686a8d08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="edf64-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="edf64-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="edf64-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="edf64-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf64-104">语法</span><span class="sxs-lookup"><span data-stu-id="edf64-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="edf64-105">方法</span><span class="sxs-lookup"><span data-stu-id="edf64-105">Methods</span></span>  
 <span data-ttu-id="edf64-106">BinaryMessageEncodingBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="edf64-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="edf64-107">属性</span><span class="sxs-lookup"><span data-stu-id="edf64-107">Properties</span></span>  
 <span data-ttu-id="edf64-108">BinaryMessageEncodingBindingElement 类具有下列属性。</span><span class="sxs-lookup"><span data-stu-id="edf64-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="edf64-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="edf64-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="edf64-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="edf64-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="edf64-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="edf64-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edf64-112">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="edf64-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="edf64-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="edf64-113">MaxSessionSize</span></span>  
 <span data-ttu-id="edf64-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="edf64-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="edf64-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="edf64-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edf64-116">一个值，指定用于编码的缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="edf64-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="edf64-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="edf64-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="edf64-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="edf64-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="edf64-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="edf64-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edf64-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="edf64-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="edf64-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="edf64-121">ReaderQuotas</span></span>  
 <span data-ttu-id="edf64-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="edf64-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="edf64-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="edf64-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edf64-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="edf64-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edf64-125">要求</span><span class="sxs-lookup"><span data-stu-id="edf64-125">Requirements</span></span>  
  
|<span data-ttu-id="edf64-126">MOF</span><span class="sxs-lookup"><span data-stu-id="edf64-126">MOF</span></span>|<span data-ttu-id="edf64-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="edf64-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="edf64-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="edf64-128">Namespace</span></span>|<span data-ttu-id="edf64-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="edf64-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edf64-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edf64-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
