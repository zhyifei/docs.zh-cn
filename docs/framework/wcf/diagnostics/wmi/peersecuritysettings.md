---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: c74ee82d7aa3a23f0ee6a69185ad45857c31bb0b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087874"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="4993f-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4993f-102">PeerSecuritySettings</span></span>
<span data-ttu-id="4993f-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4993f-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4993f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4993f-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4993f-105">方法</span><span class="sxs-lookup"><span data-stu-id="4993f-105">Methods</span></span>  
 <span data-ttu-id="4993f-106">PeerSecuritySettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="4993f-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4993f-107">属性</span><span class="sxs-lookup"><span data-stu-id="4993f-107">Properties</span></span>  
 <span data-ttu-id="4993f-108">PeerSecuritySettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="4993f-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="4993f-109">模式</span><span class="sxs-lookup"><span data-stu-id="4993f-109">Mode</span></span>  
 <span data-ttu-id="4993f-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="4993f-110">Data type: string</span></span>  
  
 <span data-ttu-id="4993f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="4993f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4993f-112">配置有绑定的终结点是否使用消息级别和传输级别安全。</span><span class="sxs-lookup"><span data-stu-id="4993f-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="4993f-113">传输</span><span class="sxs-lookup"><span data-stu-id="4993f-113">Transport</span></span>  
 <span data-ttu-id="4993f-114">数据类型：PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4993f-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="4993f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="4993f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4993f-116">传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="4993f-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4993f-117">要求</span><span class="sxs-lookup"><span data-stu-id="4993f-117">Requirements</span></span>  
  
|<span data-ttu-id="4993f-118">MOF</span><span class="sxs-lookup"><span data-stu-id="4993f-118">MOF</span></span>|<span data-ttu-id="4993f-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="4993f-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4993f-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="4993f-120">Namespace</span></span>|<span data-ttu-id="4993f-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="4993f-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4993f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4993f-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
