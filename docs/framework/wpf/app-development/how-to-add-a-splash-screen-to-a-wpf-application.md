---
title: 如何：将初始屏幕添加到 WPF 应用程序
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 46efa041736870c5c0f08baa321ef0dc53cacc0d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502749"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="82adb-102">如何：将初始屏幕添加到 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="82adb-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="82adb-103">本主题演示如何将添加一个启动窗口中，或*初始屏幕*，到 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="82adb-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="82adb-104">若要将现有映像添加为初始屏幕</span><span class="sxs-lookup"><span data-stu-id="82adb-104">To add an existing image as a splash screen</span></span>

1.  <span data-ttu-id="82adb-105">创建或查找想要用于初始屏幕的图像。</span><span class="sxs-lookup"><span data-stu-id="82adb-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="82adb-106">可以使用任何支持的 Windows Imaging Component (WIC) 的图像格式。</span><span class="sxs-lookup"><span data-stu-id="82adb-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="82adb-107">例如，可以使用 BMP、 GIF、 JPEG、 PNG 或 TIFF 格式。</span><span class="sxs-lookup"><span data-stu-id="82adb-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2.  <span data-ttu-id="82adb-108">将图像文件添加到 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="82adb-108">Add the image file to the WPF Application project.</span></span>

3.  <span data-ttu-id="82adb-109">在中**解决方案资源管理器**，选择的映像。</span><span class="sxs-lookup"><span data-stu-id="82adb-109">In **Solution Explorer**, select the image.</span></span>

4.  <span data-ttu-id="82adb-110">在属性窗口中，单击下拉箭头**生成操作**属性。</span><span class="sxs-lookup"><span data-stu-id="82adb-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5.  <span data-ttu-id="82adb-111">选择**初始屏幕**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="82adb-111">Select **SplashScreen** from the drop-down list.</span></span>

6.  <span data-ttu-id="82adb-112">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="82adb-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="82adb-113">初始屏幕图像显示在屏幕上，在中心，然后淡主应用程序窗口出现时。</span><span class="sxs-lookup"><span data-stu-id="82adb-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="82adb-114">若要从生成中排除的初始屏幕</span><span class="sxs-lookup"><span data-stu-id="82adb-114">To exclude the splash screen from build</span></span>

1.  <span data-ttu-id="82adb-115">在中**解决方案资源管理器**，选择初始屏幕图像。</span><span class="sxs-lookup"><span data-stu-id="82adb-115">In **Solution Explorer**, select the splash screen image.</span></span>

2.  <span data-ttu-id="82adb-116">在中**属性**窗口中，将**生成操作**到**None**。</span><span class="sxs-lookup"><span data-stu-id="82adb-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="82adb-117">若要删除从应用程序的初始屏幕</span><span class="sxs-lookup"><span data-stu-id="82adb-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="82adb-118">在中**解决方案资源管理器**，删除初始屏幕图像。</span><span class="sxs-lookup"><span data-stu-id="82adb-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="82adb-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="82adb-119">See Also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="82adb-120">[如何： 向项目添加现有项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="82adb-120">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
