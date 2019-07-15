---
ms.openlocfilehash: d00f86c492a7d32344b1067a48c8e53aa2a43426
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858511"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="2ff44-101">反射对象可能无法再从托管代码传递至进程外 DCOM 客户端</span><span class="sxs-lookup"><span data-stu-id="2ff44-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2ff44-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="2ff44-102">Details</span></span>|<span data-ttu-id="2ff44-103">反射对象可能无法再从托管代码传道至进程外客户端</span><span class="sxs-lookup"><span data-stu-id="2ff44-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="2ff44-104">以下类型将受影响：</span><span class="sxs-lookup"><span data-stu-id="2ff44-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><span data-ttu-id="2ff44-105"><xref:System.Reflection.MemberInfo?displayProperty=name>（及其派生类型，包括 <xref:System.Reflection.FieldInfo?displayProperty=name>、<xref:System.Reflection.MethodInfo?displayProperty=name>、<xref:System.Type?displayProperty=name> 和 <xref:System.Reflection.TypeInfo?displayProperty=name>）</span><span class="sxs-lookup"><span data-stu-id="2ff44-105"><xref:System.Reflection.MemberInfo?displayProperty=name> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name>, and <xref:System.Reflection.TypeInfo?displayProperty=name>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><span data-ttu-id="2ff44-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="2ff44-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>.</span></span></li></ul><span data-ttu-id="2ff44-107">调用对象的 <code>IMarshal</code> 会返回 <code>E_NOINTERFACE</code>。</span><span class="sxs-lookup"><span data-stu-id="2ff44-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>|
|<span data-ttu-id="2ff44-108">建议</span><span class="sxs-lookup"><span data-stu-id="2ff44-108">Suggestion</span></span>|<span data-ttu-id="2ff44-109">更新封送代码，以与非反射对象一起使用</span><span class="sxs-lookup"><span data-stu-id="2ff44-109">Update marshaling code to work with non-reflection objects</span></span>|
|<span data-ttu-id="2ff44-110">范围</span><span class="sxs-lookup"><span data-stu-id="2ff44-110">Scope</span></span>|<span data-ttu-id="2ff44-111">次要</span><span class="sxs-lookup"><span data-stu-id="2ff44-111">Minor</span></span>|
|<span data-ttu-id="2ff44-112">版本</span><span class="sxs-lookup"><span data-stu-id="2ff44-112">Version</span></span>|<span data-ttu-id="2ff44-113">4.6</span><span class="sxs-lookup"><span data-stu-id="2ff44-113">4.6</span></span>|
|<span data-ttu-id="2ff44-114">类型</span><span class="sxs-lookup"><span data-stu-id="2ff44-114">Type</span></span>|<span data-ttu-id="2ff44-115">运行时</span><span class="sxs-lookup"><span data-stu-id="2ff44-115">Runtime</span></span>|

