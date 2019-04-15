---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236117"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="7c89d-101">WPF 中改进的 Keytip 行为</span><span class="sxs-lookup"><span data-stu-id="7c89d-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7c89d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c89d-102">Details</span></span>|<span data-ttu-id="7c89d-103">已修改 Keytip 行为，以便对 Microsoft Word 和 Windows 资源管理器行为进行奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="7c89d-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="7c89d-104">通过在按下 <xref:System.Windows.Input.KeyEventArgs.SystemKey>（特别是 <xref:System.Windows.Input.Key> 或 <xref:System.Windows.Input.Key.F11>）的情况下检查是否启用 keytip 状态，WPF 可正确地处理 keytip 键。</span><span class="sxs-lookup"><span data-stu-id="7c89d-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="7c89d-105">现在，即使是通过鼠标打开的菜单，keytip 也可将其关闭。</span><span class="sxs-lookup"><span data-stu-id="7c89d-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="7c89d-106">建议</span><span class="sxs-lookup"><span data-stu-id="7c89d-106">Suggestion</span></span>|<span data-ttu-id="7c89d-107">不可用</span><span class="sxs-lookup"><span data-stu-id="7c89d-107">N/A</span></span>|
|<span data-ttu-id="7c89d-108">范围</span><span class="sxs-lookup"><span data-stu-id="7c89d-108">Scope</span></span>|<span data-ttu-id="7c89d-109">边缘</span><span class="sxs-lookup"><span data-stu-id="7c89d-109">Edge</span></span>|
|<span data-ttu-id="7c89d-110">版本</span><span class="sxs-lookup"><span data-stu-id="7c89d-110">Version</span></span>|<span data-ttu-id="7c89d-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="7c89d-111">4.7.2</span></span>|
|<span data-ttu-id="7c89d-112">类型</span><span class="sxs-lookup"><span data-stu-id="7c89d-112">Type</span></span>|<span data-ttu-id="7c89d-113">运行时</span><span class="sxs-lookup"><span data-stu-id="7c89d-113">Runtime</span></span>|
