---
title: SecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b567c173c5a04421bce57585d96b8b45144c5625
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="securitybindingelement"></a><span data-ttu-id="05204-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="05204-102">SecurityBindingElement</span></span>
<span data-ttu-id="05204-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="05204-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05204-104">语法</span><span class="sxs-lookup"><span data-stu-id="05204-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="05204-105">方法</span><span class="sxs-lookup"><span data-stu-id="05204-105">Methods</span></span>  
 <span data-ttu-id="05204-106">SecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="05204-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="05204-107">属性</span><span class="sxs-lookup"><span data-stu-id="05204-107">Properties</span></span>  
 <span data-ttu-id="05204-108">SecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="05204-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="05204-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="05204-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="05204-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="05204-110">Data type: string</span></span>  
  
 <span data-ttu-id="05204-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-112">指定要用于绑定的算法。</span><span class="sxs-lookup"><span data-stu-id="05204-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="05204-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="05204-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="05204-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="05204-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="05204-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-116">一个布尔值，指定是否每个消息都包含时间戳。</span><span class="sxs-lookup"><span data-stu-id="05204-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="05204-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="05204-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="05204-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="05204-118">Data type: string</span></span>  
  
 <span data-ttu-id="05204-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-120">用于创建密钥的熵的来源。</span><span class="sxs-lookup"><span data-stu-id="05204-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="05204-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="05204-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="05204-122">数据类型：LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="05204-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="05204-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-124">本地服务的特定于绑定的安全属性。</span><span class="sxs-lookup"><span data-stu-id="05204-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="05204-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="05204-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="05204-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="05204-126">Data type: string</span></span>  
  
 <span data-ttu-id="05204-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-128">消息安全使用的版本。</span><span class="sxs-lookup"><span data-stu-id="05204-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="05204-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="05204-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="05204-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="05204-130">Data type: string</span></span>  
  
 <span data-ttu-id="05204-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="05204-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05204-132">此绑定的安全标头中的元素顺序。</span><span class="sxs-lookup"><span data-stu-id="05204-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05204-133">要求</span><span class="sxs-lookup"><span data-stu-id="05204-133">Requirements</span></span>  
  
|<span data-ttu-id="05204-134">MOF</span><span class="sxs-lookup"><span data-stu-id="05204-134">MOF</span></span>|<span data-ttu-id="05204-135">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="05204-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="05204-136">命名空间</span><span class="sxs-lookup"><span data-stu-id="05204-136">Namespace</span></span>|<span data-ttu-id="05204-137">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="05204-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05204-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05204-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
