---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="5bdcd-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="5bdcd-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="5bdcd-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="5bdcd-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdcd-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bdcd-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5bdcd-105">方法</span><span class="sxs-lookup"><span data-stu-id="5bdcd-105">Methods</span></span>  
 <span data-ttu-id="5bdcd-106">TransactionFlowBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5bdcd-107">属性</span><span class="sxs-lookup"><span data-stu-id="5bdcd-107">Properties</span></span>  
 <span data-ttu-id="5bdcd-108">TransactionFlowBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="5bdcd-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="5bdcd-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="5bdcd-109">IssuedTokens</span></span>  
 <span data-ttu-id="5bdcd-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5bdcd-110">Data type: string</span></span>  
  
 <span data-ttu-id="5bdcd-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5bdcd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bdcd-112">指定对已颁发的安全令牌标头（来自 WS-Trust 的 IssuedTokens）的要求。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="5bdcd-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="5bdcd-113">TransactionProtocol</span></span>  
 <span data-ttu-id="5bdcd-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5bdcd-114">Data type: string</span></span>  
  
 <span data-ttu-id="5bdcd-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5bdcd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bdcd-116">对事务进行流处理时使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="5bdcd-117">事务</span><span class="sxs-lookup"><span data-stu-id="5bdcd-117">Transactions</span></span>  
 <span data-ttu-id="5bdcd-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="5bdcd-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="5bdcd-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5bdcd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bdcd-120">指示是否支持传入事务。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bdcd-121">要求</span><span class="sxs-lookup"><span data-stu-id="5bdcd-121">Requirements</span></span>  
  
|<span data-ttu-id="5bdcd-122">MOF</span><span class="sxs-lookup"><span data-stu-id="5bdcd-122">MOF</span></span>|<span data-ttu-id="5bdcd-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5bdcd-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="5bdcd-124">Namespace</span></span>|<span data-ttu-id="5bdcd-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="5bdcd-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bdcd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bdcd-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
