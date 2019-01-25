---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 188a766807cd779ac51df390b1332641584dbb06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662707"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="b1edc-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1edc-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="b1edc-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b1edc-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1edc-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1edc-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1edc-105">方法</span><span class="sxs-lookup"><span data-stu-id="b1edc-105">Methods</span></span>  
 <span data-ttu-id="b1edc-106">TextMessageEncodingBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b1edc-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1edc-107">Properties</span><span class="sxs-lookup"><span data-stu-id="b1edc-107">Properties</span></span>  
 <span data-ttu-id="b1edc-108">TextMessageEncodingBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="b1edc-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="b1edc-109">编码</span><span class="sxs-lookup"><span data-stu-id="b1edc-109">Encoding</span></span>  
 <span data-ttu-id="b1edc-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b1edc-110">Data type: string</span></span>  
  
 <span data-ttu-id="b1edc-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b1edc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1edc-112">要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="b1edc-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="b1edc-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="b1edc-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="b1edc-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b1edc-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b1edc-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b1edc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1edc-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="b1edc-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="b1edc-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="b1edc-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="b1edc-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b1edc-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b1edc-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b1edc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1edc-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="b1edc-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="b1edc-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b1edc-121">ReaderQuotas</span></span>  
 <span data-ttu-id="b1edc-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b1edc-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="b1edc-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b1edc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1edc-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="b1edc-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1edc-125">要求</span><span class="sxs-lookup"><span data-stu-id="b1edc-125">Requirements</span></span>  
  
|<span data-ttu-id="b1edc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b1edc-126">MOF</span></span>|<span data-ttu-id="b1edc-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b1edc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b1edc-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="b1edc-128">Namespace</span></span>|<span data-ttu-id="b1edc-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b1edc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1edc-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1edc-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
