---
title: 如何：将初始屏幕添加到 WPF 应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 06d6cb7c5a5081d3b6c4979ab50e1caaa726acbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546996"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="d4857-102">如何：将初始屏幕添加到 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="d4857-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="d4857-103">本主题演示如何将添加一个启动窗口中，或*初始屏幕*，到 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4857-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="d4857-104">若要将现有映像添加为初始屏幕</span><span class="sxs-lookup"><span data-stu-id="d4857-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="d4857-105">创建或查找你想要用于初始屏幕的映像。</span><span class="sxs-lookup"><span data-stu-id="d4857-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="d4857-106">你可以使用任何图像格式受支持的 Windows 映像组件 (WIC)。</span><span class="sxs-lookup"><span data-stu-id="d4857-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="d4857-107">例如，你可以使用 BMP、 GIF、 JPEG、 PNG 或 TIFF 格式。</span><span class="sxs-lookup"><span data-stu-id="d4857-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="d4857-108">将图像文件添加到 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="d4857-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="d4857-109">有关详细信息，请参阅[NIB： 如何： 将现有项目添加到项目](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)。</span><span class="sxs-lookup"><span data-stu-id="d4857-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="d4857-110">在解决方案资源管理器，选择映像。</span><span class="sxs-lookup"><span data-stu-id="d4857-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="d4857-111">在属性窗口中，单击下拉箭头**生成操作**属性。</span><span class="sxs-lookup"><span data-stu-id="d4857-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="d4857-112">选择**初始屏幕**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d4857-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4857-113">如果看不到**初始屏幕**选项，请务必检查你正在使用[!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d4857-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="d4857-114">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4857-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="d4857-115">初始屏幕图像出现在该屏幕的中心，然后淡主应用程序窗口出现时。</span><span class="sxs-lookup"><span data-stu-id="d4857-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="d4857-116">若要删除从应用程序的初始屏幕</span><span class="sxs-lookup"><span data-stu-id="d4857-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="d4857-117">在解决方案资源管理器，选择初始屏幕图像。</span><span class="sxs-lookup"><span data-stu-id="d4857-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="d4857-118">在属性窗口中，设置**生成操作**到**无**。</span><span class="sxs-lookup"><span data-stu-id="d4857-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="d4857-119">若要删除从应用程序的初始屏幕</span><span class="sxs-lookup"><span data-stu-id="d4857-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="d4857-120">在解决方案资源管理器，删除初始屏幕图像。</span><span class="sxs-lookup"><span data-stu-id="d4857-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="d4857-121">从项目中排除初始屏幕图像。</span><span class="sxs-lookup"><span data-stu-id="d4857-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4857-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4857-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="d4857-123">NIB： 如何： 将现有项添加到项目</span><span class="sxs-lookup"><span data-stu-id="d4857-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
