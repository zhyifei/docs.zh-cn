---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979012"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="b631e-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b631e-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="b631e-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="b631e-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b631e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b631e-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b631e-105">方法</span><span class="sxs-lookup"><span data-stu-id="b631e-105">Methods</span></span>  
 <span data-ttu-id="b631e-106">TextMessageEncodingBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b631e-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b631e-107">属性</span><span class="sxs-lookup"><span data-stu-id="b631e-107">Properties</span></span>  
 <span data-ttu-id="b631e-108">TextMessageEncodingBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="b631e-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="b631e-109">编码</span><span class="sxs-lookup"><span data-stu-id="b631e-109">Encoding</span></span>  
 <span data-ttu-id="b631e-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b631e-110">Data type: string</span></span>  
  
 <span data-ttu-id="b631e-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b631e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b631e-112">要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="b631e-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="b631e-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="b631e-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="b631e-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b631e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b631e-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b631e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b631e-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="b631e-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="b631e-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="b631e-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="b631e-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b631e-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b631e-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b631e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b631e-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="b631e-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="b631e-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b631e-121">ReaderQuotas</span></span>  
 <span data-ttu-id="b631e-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="b631e-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="b631e-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b631e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b631e-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="b631e-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b631e-125">要求</span><span class="sxs-lookup"><span data-stu-id="b631e-125">Requirements</span></span>  
  
|<span data-ttu-id="b631e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b631e-126">MOF</span></span>|<span data-ttu-id="b631e-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b631e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b631e-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="b631e-128">Namespace</span></span>|<span data-ttu-id="b631e-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b631e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b631e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b631e-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
