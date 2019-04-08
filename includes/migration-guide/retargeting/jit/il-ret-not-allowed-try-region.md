---
ms.openlocfilehash: 060da3ebc60057554fd572bd2569652afee6bd0f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760975"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="7cfad-101">试用区域中不允许 IL ret</span><span class="sxs-lookup"><span data-stu-id="7cfad-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7cfad-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="7cfad-102">Details</span></span>|<span data-ttu-id="7cfad-103">与 JIT64 实时编译器不同，RyuJIT（在 .NET Framework 4.6 中使用）不允许在试用区域中使用 IL ret 指令。</span><span class="sxs-lookup"><span data-stu-id="7cfad-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="7cfad-104">ECMA-335 规范不允许从试用区域返回，并且没有已知的托管编译器会生成此类 IL。</span><span class="sxs-lookup"><span data-stu-id="7cfad-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="7cfad-105">但是，如果由反射发出生成，则 JIT64 编译器执行此类 IL。</span><span class="sxs-lookup"><span data-stu-id="7cfad-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="7cfad-106">建议</span><span class="sxs-lookup"><span data-stu-id="7cfad-106">Suggestion</span></span>|<span data-ttu-id="7cfad-107">如果应用正在生成在试用区域中包含 ret 操作码的 IL，则该应用会面向 .NET Framework 4.5，使用旧的 JIT 并避免此中断。</span><span class="sxs-lookup"><span data-stu-id="7cfad-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="7cfad-108">或者，生成的 IL 可更新为在试用区域之后返回。</span><span class="sxs-lookup"><span data-stu-id="7cfad-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="7cfad-109">范围</span><span class="sxs-lookup"><span data-stu-id="7cfad-109">Scope</span></span>|<span data-ttu-id="7cfad-110">边缘</span><span class="sxs-lookup"><span data-stu-id="7cfad-110">Edge</span></span>|
|<span data-ttu-id="7cfad-111">版本</span><span class="sxs-lookup"><span data-stu-id="7cfad-111">Version</span></span>|<span data-ttu-id="7cfad-112">4.6</span><span class="sxs-lookup"><span data-stu-id="7cfad-112">4.6</span></span>|
|<span data-ttu-id="7cfad-113">类型</span><span class="sxs-lookup"><span data-stu-id="7cfad-113">Type</span></span>|<span data-ttu-id="7cfad-114">重定目标</span><span class="sxs-lookup"><span data-stu-id="7cfad-114">Retargeting</span></span>|

