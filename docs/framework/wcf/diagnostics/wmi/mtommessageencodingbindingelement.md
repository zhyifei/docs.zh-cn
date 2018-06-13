---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 83fa879fbef94e2dc9c142dfb92a51a54a7b60cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486518"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="8ed46-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="8ed46-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="8ed46-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="8ed46-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed46-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ed46-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8ed46-105">方法</span><span class="sxs-lookup"><span data-stu-id="8ed46-105">Methods</span></span>  
 <span data-ttu-id="8ed46-106">MtomMessageEncodingBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="8ed46-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8ed46-107">属性</span><span class="sxs-lookup"><span data-stu-id="8ed46-107">Properties</span></span>  
 <span data-ttu-id="8ed46-108">MtomMessageEncodingBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="8ed46-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="8ed46-109">编码</span><span class="sxs-lookup"><span data-stu-id="8ed46-109">Encoding</span></span>  
 <span data-ttu-id="8ed46-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="8ed46-110">Data type: string</span></span>  
  
 <span data-ttu-id="8ed46-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8ed46-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ed46-112">要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="8ed46-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="8ed46-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="8ed46-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="8ed46-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8ed46-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ed46-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8ed46-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ed46-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="8ed46-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="8ed46-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="8ed46-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="8ed46-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="8ed46-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ed46-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8ed46-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ed46-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="8ed46-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="8ed46-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="8ed46-121">ReaderQuotas</span></span>  
 <span data-ttu-id="8ed46-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="8ed46-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="8ed46-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8ed46-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ed46-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="8ed46-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ed46-125">要求</span><span class="sxs-lookup"><span data-stu-id="8ed46-125">Requirements</span></span>  
  
|<span data-ttu-id="8ed46-126">MOF</span><span class="sxs-lookup"><span data-stu-id="8ed46-126">MOF</span></span>|<span data-ttu-id="8ed46-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="8ed46-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8ed46-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="8ed46-128">Namespace</span></span>|<span data-ttu-id="8ed46-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="8ed46-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ed46-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ed46-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
