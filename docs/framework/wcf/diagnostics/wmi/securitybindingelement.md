---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 601e3fafd9aa876186b7f78dfdcb87a2336ddfcd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185766"
---
# <a name="securitybindingelement"></a><span data-ttu-id="38784-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="38784-102">SecurityBindingElement</span></span>
<span data-ttu-id="38784-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="38784-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38784-104">语法</span><span class="sxs-lookup"><span data-stu-id="38784-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="38784-105">方法</span><span class="sxs-lookup"><span data-stu-id="38784-105">Methods</span></span>  
 <span data-ttu-id="38784-106">SecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="38784-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="38784-107">属性</span><span class="sxs-lookup"><span data-stu-id="38784-107">Properties</span></span>  
 <span data-ttu-id="38784-108">SecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="38784-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="38784-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="38784-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="38784-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="38784-110">Data type: string</span></span>  
  
 <span data-ttu-id="38784-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-112">指定要用于绑定的算法。</span><span class="sxs-lookup"><span data-stu-id="38784-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="38784-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="38784-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="38784-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="38784-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="38784-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-116">一个布尔值，指定是否每个消息都包含时间戳。</span><span class="sxs-lookup"><span data-stu-id="38784-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="38784-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="38784-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="38784-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="38784-118">Data type: string</span></span>  
  
 <span data-ttu-id="38784-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-120">用于创建密钥的熵的来源。</span><span class="sxs-lookup"><span data-stu-id="38784-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="38784-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="38784-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="38784-122">数据类型：LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="38784-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="38784-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-124">本地服务的特定于绑定的安全属性。</span><span class="sxs-lookup"><span data-stu-id="38784-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="38784-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="38784-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="38784-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="38784-126">Data type: string</span></span>  
  
 <span data-ttu-id="38784-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-128">消息安全使用的版本。</span><span class="sxs-lookup"><span data-stu-id="38784-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="38784-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="38784-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="38784-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="38784-130">Data type: string</span></span>  
  
 <span data-ttu-id="38784-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="38784-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="38784-132">此绑定的安全标头中的元素顺序。</span><span class="sxs-lookup"><span data-stu-id="38784-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38784-133">要求</span><span class="sxs-lookup"><span data-stu-id="38784-133">Requirements</span></span>  
  
|<span data-ttu-id="38784-134">MOF</span><span class="sxs-lookup"><span data-stu-id="38784-134">MOF</span></span>|<span data-ttu-id="38784-135">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="38784-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="38784-136">命名空间</span><span class="sxs-lookup"><span data-stu-id="38784-136">Namespace</span></span>|<span data-ttu-id="38784-137">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="38784-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38784-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="38784-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
