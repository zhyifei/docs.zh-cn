---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: f9b94e946413967cc14282e85743a23327683b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486011"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="ee9c6-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ee9c6-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="ee9c6-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ee9c6-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee9c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee9c6-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ee9c6-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee9c6-105">Methods</span></span>  
 <span data-ttu-id="ee9c6-106">TextMessageEncodingBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ee9c6-107">属性</span><span class="sxs-lookup"><span data-stu-id="ee9c6-107">Properties</span></span>  
 <span data-ttu-id="ee9c6-108">TextMessageEncodingBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ee9c6-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="ee9c6-109">编码</span><span class="sxs-lookup"><span data-stu-id="ee9c6-109">Encoding</span></span>  
 <span data-ttu-id="ee9c6-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ee9c6-110">Data type: string</span></span>  
  
 <span data-ttu-id="ee9c6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee9c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee9c6-112">要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="ee9c6-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="ee9c6-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="ee9c6-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ee9c6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ee9c6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee9c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee9c6-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="ee9c6-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="ee9c6-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="ee9c6-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ee9c6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ee9c6-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee9c6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee9c6-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="ee9c6-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ee9c6-121">ReaderQuotas</span></span>  
 <span data-ttu-id="ee9c6-122">数据类型：XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ee9c6-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="ee9c6-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee9c6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee9c6-124">读取器的配额。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee9c6-125">要求</span><span class="sxs-lookup"><span data-stu-id="ee9c6-125">Requirements</span></span>  
  
|<span data-ttu-id="ee9c6-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ee9c6-126">MOF</span></span>|<span data-ttu-id="ee9c6-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ee9c6-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ee9c6-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="ee9c6-128">Namespace</span></span>|<span data-ttu-id="ee9c6-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ee9c6-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee9c6-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee9c6-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
