---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963002"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="7ed88-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7ed88-102">PeerSecuritySettings</span></span>
<span data-ttu-id="7ed88-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7ed88-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed88-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ed88-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7ed88-105">方法</span><span class="sxs-lookup"><span data-stu-id="7ed88-105">Methods</span></span>  
 <span data-ttu-id="7ed88-106">PeerSecuritySettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="7ed88-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ed88-107">属性</span><span class="sxs-lookup"><span data-stu-id="7ed88-107">Properties</span></span>  
 <span data-ttu-id="7ed88-108">PeerSecuritySettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="7ed88-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="7ed88-109">模式</span><span class="sxs-lookup"><span data-stu-id="7ed88-109">Mode</span></span>  
 <span data-ttu-id="7ed88-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7ed88-110">Data type: string</span></span>  
  
 <span data-ttu-id="7ed88-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7ed88-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ed88-112">配置有绑定的终结点是否使用消息级别和传输级别安全。</span><span class="sxs-lookup"><span data-stu-id="7ed88-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="7ed88-113">传输</span><span class="sxs-lookup"><span data-stu-id="7ed88-113">Transport</span></span>  
 <span data-ttu-id="7ed88-114">数据类型：PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7ed88-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="7ed88-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7ed88-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ed88-116">传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="7ed88-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ed88-117">要求</span><span class="sxs-lookup"><span data-stu-id="7ed88-117">Requirements</span></span>  
  
|<span data-ttu-id="7ed88-118">MOF</span><span class="sxs-lookup"><span data-stu-id="7ed88-118">MOF</span></span>|<span data-ttu-id="7ed88-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="7ed88-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7ed88-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="7ed88-120">Namespace</span></span>|<span data-ttu-id="7ed88-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="7ed88-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ed88-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed88-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
