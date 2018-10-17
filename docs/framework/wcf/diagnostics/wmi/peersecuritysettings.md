---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: 18caaf2750fa3a263c09176e975204258330752c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371623"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="18749-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="18749-102">PeerSecuritySettings</span></span>
<span data-ttu-id="18749-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="18749-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18749-104">语法</span><span class="sxs-lookup"><span data-stu-id="18749-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="18749-105">方法</span><span class="sxs-lookup"><span data-stu-id="18749-105">Methods</span></span>  
 <span data-ttu-id="18749-106">PeerSecuritySettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="18749-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="18749-107">属性</span><span class="sxs-lookup"><span data-stu-id="18749-107">Properties</span></span>  
 <span data-ttu-id="18749-108">PeerSecuritySettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="18749-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="18749-109">模式</span><span class="sxs-lookup"><span data-stu-id="18749-109">Mode</span></span>  
 <span data-ttu-id="18749-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="18749-110">Data type: string</span></span>  
  
 <span data-ttu-id="18749-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18749-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18749-112">配置有绑定的终结点是否使用消息级别和传输级别安全。</span><span class="sxs-lookup"><span data-stu-id="18749-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="18749-113">传输</span><span class="sxs-lookup"><span data-stu-id="18749-113">Transport</span></span>  
 <span data-ttu-id="18749-114">数据类型：PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="18749-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="18749-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18749-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18749-116">传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="18749-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18749-117">要求</span><span class="sxs-lookup"><span data-stu-id="18749-117">Requirements</span></span>  
  
|<span data-ttu-id="18749-118">MOF</span><span class="sxs-lookup"><span data-stu-id="18749-118">MOF</span></span>|<span data-ttu-id="18749-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="18749-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="18749-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="18749-120">Namespace</span></span>|<span data-ttu-id="18749-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="18749-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18749-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="18749-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
