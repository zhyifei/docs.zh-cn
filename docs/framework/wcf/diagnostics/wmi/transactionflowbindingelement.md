---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514564"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="b4c0f-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b4c0f-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="b4c0f-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="b4c0f-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4c0f-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b4c0f-105">方法</span><span class="sxs-lookup"><span data-stu-id="b4c0f-105">Methods</span></span>  
 <span data-ttu-id="b4c0f-106">TransactionFlowBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b4c0f-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b4c0f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="b4c0f-107">Properties</span></span>  
 <span data-ttu-id="b4c0f-108">TransactionFlowBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b4c0f-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="b4c0f-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="b4c0f-109">IssuedTokens</span></span>  
 <span data-ttu-id="b4c0f-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b4c0f-110">Data type: string</span></span>  
  
 <span data-ttu-id="b4c0f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b4c0f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4c0f-112">指定对已颁发的安全令牌标头（来自 WS-Trust 的 IssuedTokens）的需求。</span><span class="sxs-lookup"><span data-stu-id="b4c0f-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="b4c0f-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="b4c0f-113">TransactionProtocol</span></span>  
 <span data-ttu-id="b4c0f-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b4c0f-114">Data type: string</span></span>  
  
 <span data-ttu-id="b4c0f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b4c0f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4c0f-116">对事务进行流处理时使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="b4c0f-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="b4c0f-117">事务</span><span class="sxs-lookup"><span data-stu-id="b4c0f-117">Transactions</span></span>  
 <span data-ttu-id="b4c0f-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b4c0f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b4c0f-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b4c0f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4c0f-120">指示是否支持传入事务。</span><span class="sxs-lookup"><span data-stu-id="b4c0f-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c0f-121">要求</span><span class="sxs-lookup"><span data-stu-id="b4c0f-121">Requirements</span></span>  
  
|<span data-ttu-id="b4c0f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b4c0f-122">MOF</span></span>|<span data-ttu-id="b4c0f-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b4c0f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b4c0f-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b4c0f-124">Namespace</span></span>|<span data-ttu-id="b4c0f-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b4c0f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4c0f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4c0f-126">See also</span></span>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
