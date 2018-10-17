---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: bd6d22635c4403e0526270a4ee50cf809c88989b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371063"
---
# <a name="securitybindingelement"></a><span data-ttu-id="9321d-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9321d-102">SecurityBindingElement</span></span>
<span data-ttu-id="9321d-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9321d-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9321d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9321d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9321d-105">方法</span><span class="sxs-lookup"><span data-stu-id="9321d-105">Methods</span></span>  
 <span data-ttu-id="9321d-106">SecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="9321d-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9321d-107">属性</span><span class="sxs-lookup"><span data-stu-id="9321d-107">Properties</span></span>  
 <span data-ttu-id="9321d-108">SecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="9321d-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="9321d-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9321d-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="9321d-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9321d-110">Data type: string</span></span>  
  
 <span data-ttu-id="9321d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-112">指定要用于绑定的算法。</span><span class="sxs-lookup"><span data-stu-id="9321d-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="9321d-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="9321d-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="9321d-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="9321d-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9321d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-116">一个布尔值，指定是否每个消息都包含时间戳。</span><span class="sxs-lookup"><span data-stu-id="9321d-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="9321d-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="9321d-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="9321d-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9321d-118">Data type: string</span></span>  
  
 <span data-ttu-id="9321d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-120">用于创建密钥的熵的来源。</span><span class="sxs-lookup"><span data-stu-id="9321d-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="9321d-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9321d-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="9321d-122">数据类型：LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9321d-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="9321d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-124">本地服务的特定于绑定的安全属性。</span><span class="sxs-lookup"><span data-stu-id="9321d-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="9321d-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="9321d-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="9321d-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9321d-126">Data type: string</span></span>  
  
 <span data-ttu-id="9321d-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-128">消息安全使用的版本。</span><span class="sxs-lookup"><span data-stu-id="9321d-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="9321d-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="9321d-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="9321d-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9321d-130">Data type: string</span></span>  
  
 <span data-ttu-id="9321d-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9321d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9321d-132">此绑定的安全标头中的元素顺序。</span><span class="sxs-lookup"><span data-stu-id="9321d-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9321d-133">要求</span><span class="sxs-lookup"><span data-stu-id="9321d-133">Requirements</span></span>  
  
|<span data-ttu-id="9321d-134">MOF</span><span class="sxs-lookup"><span data-stu-id="9321d-134">MOF</span></span>|<span data-ttu-id="9321d-135">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="9321d-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9321d-136">命名空间</span><span class="sxs-lookup"><span data-stu-id="9321d-136">Namespace</span></span>|<span data-ttu-id="9321d-137">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="9321d-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9321d-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="9321d-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
