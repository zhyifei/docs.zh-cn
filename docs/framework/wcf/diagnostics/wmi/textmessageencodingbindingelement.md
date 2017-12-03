---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 966f1ae06f5d7e0dacb8b7d450463c75f783ef1f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="73b1c-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="73b1c-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="73b1c-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="73b1c-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="73b1c-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="73b1c-105">方法</span><span class="sxs-lookup"><span data-stu-id="73b1c-105">Methods</span></span>  
 <span data-ttu-id="73b1c-106">TextMessageEncodingBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="73b1c-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="73b1c-107">属性</span><span class="sxs-lookup"><span data-stu-id="73b1c-107">Properties</span></span>  
 <span data-ttu-id="73b1c-108">TextMessageEncodingBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="73b1c-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="73b1c-109">编码</span><span class="sxs-lookup"><span data-stu-id="73b1c-109">Encoding</span></span>  
 <span data-ttu-id="73b1c-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="73b1c-110">Data type: string</span></span>  
  
 <span data-ttu-id="73b1c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="73b1c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73b1c-112">要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="73b1c-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="73b1c-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="73b1c-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="73b1c-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="73b1c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="73b1c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="73b1c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73b1c-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="73b1c-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="73b1c-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="73b1c-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="73b1c-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="73b1c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="73b1c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="73b1c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73b1c-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="73b1c-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="73b1c-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="73b1c-121">ReaderQuotas</span></span>  
 <span data-ttu-id="73b1c-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="73b1c-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="73b1c-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="73b1c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="73b1c-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="73b1c-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73b1c-125">要求</span><span class="sxs-lookup"><span data-stu-id="73b1c-125">Requirements</span></span>  
  
|<span data-ttu-id="73b1c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="73b1c-126">MOF</span></span>|<span data-ttu-id="73b1c-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="73b1c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="73b1c-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="73b1c-128">Namespace</span></span>|<span data-ttu-id="73b1c-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="73b1c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73b1c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73b1c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
