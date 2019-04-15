---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235157"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="f46db-101">对于 System.Drawing，WinForm 的 CheckForOverflowUnderflow 属性现在为 true</span><span class="sxs-lookup"><span data-stu-id="f46db-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f46db-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f46db-102">Details</span></span>|<span data-ttu-id="f46db-103">System.Drawing.dll 程序集的 CheckForOverflowUnderflow 设置为 true。</span><span class="sxs-lookup"><span data-stu-id="f46db-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="f46db-104">建议</span><span class="sxs-lookup"><span data-stu-id="f46db-104">Suggestion</span></span>|<span data-ttu-id="f46db-105">之前在发生溢出时，结果会在不提示的情况下被截断。</span><span class="sxs-lookup"><span data-stu-id="f46db-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="f46db-106">现在引发了 <xref:System.OverflowException?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="f46db-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="f46db-107">范围</span><span class="sxs-lookup"><span data-stu-id="f46db-107">Scope</span></span>|<span data-ttu-id="f46db-108">边缘</span><span class="sxs-lookup"><span data-stu-id="f46db-108">Edge</span></span>|
|<span data-ttu-id="f46db-109">版本</span><span class="sxs-lookup"><span data-stu-id="f46db-109">Version</span></span>|<span data-ttu-id="f46db-110">4.5</span><span class="sxs-lookup"><span data-stu-id="f46db-110">4.5</span></span>|
|<span data-ttu-id="f46db-111">类型</span><span class="sxs-lookup"><span data-stu-id="f46db-111">Type</span></span>|<span data-ttu-id="f46db-112">运行时</span><span class="sxs-lookup"><span data-stu-id="f46db-112">Runtime</span></span>|
