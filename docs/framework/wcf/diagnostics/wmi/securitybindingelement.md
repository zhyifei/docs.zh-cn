---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962781"
---
# <a name="securitybindingelement"></a><span data-ttu-id="9dc0f-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9dc0f-102">SecurityBindingElement</span></span>
<span data-ttu-id="9dc0f-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9dc0f-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9dc0f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9dc0f-105">方法</span><span class="sxs-lookup"><span data-stu-id="9dc0f-105">Methods</span></span>  
 <span data-ttu-id="9dc0f-106">SecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9dc0f-107">属性</span><span class="sxs-lookup"><span data-stu-id="9dc0f-107">Properties</span></span>  
 <span data-ttu-id="9dc0f-108">SecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="9dc0f-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="9dc0f-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9dc0f-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="9dc0f-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9dc0f-110">Data type: string</span></span>  
  
 <span data-ttu-id="9dc0f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-112">指定要用于绑定的算法。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="9dc0f-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="9dc0f-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="9dc0f-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="9dc0f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9dc0f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-116">一个布尔值，指定是否每个消息都包含时间戳。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="9dc0f-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="9dc0f-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="9dc0f-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9dc0f-118">Data type: string</span></span>  
  
 <span data-ttu-id="9dc0f-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-120">用于创建密钥的熵的来源。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="9dc0f-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9dc0f-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="9dc0f-122">数据类型：LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9dc0f-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="9dc0f-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-124">本地服务的特定于绑定的安全属性。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="9dc0f-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="9dc0f-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="9dc0f-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9dc0f-126">Data type: string</span></span>  
  
 <span data-ttu-id="9dc0f-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-128">消息安全使用的版本。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="9dc0f-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="9dc0f-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="9dc0f-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9dc0f-130">Data type: string</span></span>  
  
 <span data-ttu-id="9dc0f-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9dc0f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9dc0f-132">此绑定的安全标头中的元素顺序。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc0f-133">要求</span><span class="sxs-lookup"><span data-stu-id="9dc0f-133">Requirements</span></span>  
  
|<span data-ttu-id="9dc0f-134">MOF</span><span class="sxs-lookup"><span data-stu-id="9dc0f-134">MOF</span></span>|<span data-ttu-id="9dc0f-135">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="9dc0f-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9dc0f-136">命名空间</span><span class="sxs-lookup"><span data-stu-id="9dc0f-136">Namespace</span></span>|<span data-ttu-id="9dc0f-137">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="9dc0f-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dc0f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dc0f-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
