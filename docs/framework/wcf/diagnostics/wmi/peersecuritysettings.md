---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="a0747-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a0747-102">PeerSecuritySettings</span></span>
<span data-ttu-id="a0747-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a0747-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0747-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0747-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a0747-105">方法</span><span class="sxs-lookup"><span data-stu-id="a0747-105">Methods</span></span>  
 <span data-ttu-id="a0747-106">PeerSecuritySettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="a0747-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a0747-107">属性</span><span class="sxs-lookup"><span data-stu-id="a0747-107">Properties</span></span>  
 <span data-ttu-id="a0747-108">PeerSecuritySettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="a0747-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="a0747-109">模式</span><span class="sxs-lookup"><span data-stu-id="a0747-109">Mode</span></span>  
 <span data-ttu-id="a0747-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="a0747-110">Data type: string</span></span>  
  
 <span data-ttu-id="a0747-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a0747-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0747-112">配置有绑定的终结点是否使用消息级别和传输级别安全。</span><span class="sxs-lookup"><span data-stu-id="a0747-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="a0747-113">传输</span><span class="sxs-lookup"><span data-stu-id="a0747-113">Transport</span></span>  
 <span data-ttu-id="a0747-114">数据类型：PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a0747-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="a0747-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a0747-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0747-116">传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="a0747-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0747-117">惠?</span><span class="sxs-lookup"><span data-stu-id="a0747-117">Requirements</span></span>  
  
|<span data-ttu-id="a0747-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a0747-118">MOF</span></span>|<span data-ttu-id="a0747-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="a0747-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a0747-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="a0747-120">Namespace</span></span>|<span data-ttu-id="a0747-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="a0747-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0747-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0747-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
