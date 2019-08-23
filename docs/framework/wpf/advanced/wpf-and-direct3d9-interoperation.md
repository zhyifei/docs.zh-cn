---
title: WPF 和 Direct3D9 互操作
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 5fccd49b4f6fa64e5902197423d732ba0b31790e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917438"
---
# <a name="wpf-and-direct3d9-interoperation"></a>WPF 和 Direct3D9 互操作
可以在 Windows Presentation Foundation (WPF) 应用程序中包含 Direct3D9 内容。 本主题介绍如何创建 Direct3D9 内容, 以便与 WPF 有效地进行互操作。  
  
> [!NOTE]
> 在 WPF 中使用 Direct3D9 内容时, 还需要考虑性能。 有关如何优化性能的详细信息, 请参阅[Direct3D9 和 WPF 互操作性的性能注意事项](performance-considerations-for-direct3d9-and-wpf-interoperability.md)。  
  
## <a name="display-buffers"></a>显示缓冲区  
 类管理两个显示缓冲区, 这些缓冲区称为*后台*缓冲区和*前台缓冲区。* <xref:System.Windows.Interop.D3DImage> 后台缓冲区是 Direct3D9 图面。 当调用<xref:System.Windows.Interop.D3DImage.Unlock%2A>方法时, 对后台缓冲区的更改将被转发到前台缓冲区。  
  
 下图显示了后台缓冲区和前台缓冲区之间的关系。  
  
 ![D3DImage 显示缓冲区](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Direct3D9 设备创建  
 若要呈现 Direct3D9 内容, 必须创建 Direct3D9 设备。 有两个可用于创建设备`IDirect3D9`的 Direct3D9 对象和。 `IDirect3D9Ex` 分别使用这些对象创建`IDirect3DDevice9`和`IDirect3DDevice9Ex`设备。  
  
 通过调用以下方法之一来创建设备。  
  
- `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
- `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 在 Windows Vista 或更高版本的操作系统上`Direct3DCreate9Ex` , 将方法与配置为使用 Windows 显示驱动程序模型 (WDDM) 的显示一起使用。 在任何其他平台上使用方法。`Direct3DCreate9`  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Direct3DCreate9Ex 方法的可用性  
 D3d9 在 Windows Vista 或更`Direct3DCreate9Ex`高版本的操作系统上只具有方法。 如果直接链接 Windows XP 上的函数, 应用程序将无法加载。 若要确定该`Direct3DCreate9Ex`方法是否受支持, 请加载该 DLL 并查找进程地址。 下面的代码演示如何测试`Direct3DCreate9Ex`方法。 有关完整的代码示例, 请[参阅演练:创建用于在 WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)中承载的 Direct3D9 内容。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>HWND 创建  
 创建设备需要 HWND。 通常, 为 Direct3D9 创建要使用的虚拟 HWND。 下面的代码示例演示如何创建虚拟 HWND。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>当前参数  
 创建设备还需要`D3DPRESENT_PARAMETERS`结构, 但只有几个参数是重要的。 选择这些参数可最大程度地减少内存占用量。  
  
 `BackBufferHeight`将和`BackBufferWidth`字段设置为1。 如果将其设置为 0, 则会将其设置为 HWND 的尺寸。  
  
 始终设置`D3DCREATE_MULTITHREADED`和`D3DCREATE_FPU_PRESERVE`标志, 以防止 Direct3D9 使用的内存损坏, 并阻止 Direct3D9 更改 FPU 设置。  
  
 下面的代码演示如何初始化`D3DPRESENT_PARAMETERS`结构。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>创建后台缓冲区呈现目标  
 若要在<xref:System.Windows.Interop.D3DImage>中显示 Direct3D9 内容, 可通过<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>调用方法来创建 Direct3D9 图面并进行分配。  
  
### <a name="verifying-adapter-support"></a>验证适配器支持  
 创建图面之前, 请验证所有适配器是否支持所需的曲面属性。 即使仅呈现到一个适配器, WPF 窗口也可能会显示在系统中的任何适配器上。 应始终编写处理多适配器配置的 Direct3D9 代码, 并且应检查所有适配器的支持, 因为 WPF 可能在可用适配器之间移动图面。  
  
 下面的代码示例演示如何在系统上检查所有适配器的 Direct3D9 支持。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>创建图面  
 创建图面之前, 请先验证设备功能是否支持目标操作系统的良好性能。 有关详细信息, 请参阅[Direct3D9 和 WPF 互操作性的性能注意事项](performance-considerations-for-direct3d9-and-wpf-interoperability.md)。  
  
 验证设备功能后, 可以创建图面。 下面的代码示例演示如何创建呈现器目标。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 在配置为使用 WDDM 的 Windows Vista 和更高版本的操作系统上, 可以创建呈现目标纹理并将级别0图面传递给<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>方法。 不建议在 Windows XP 上使用此方法, 因为无法创建可锁定的呈现目标纹理并且将降低性能。  
  
## <a name="handling-device-state"></a>处理设备状态  
 类管理两个显示缓冲区, 这些缓冲区称为*后台*缓冲区和*前台缓冲区。* <xref:System.Windows.Interop.D3DImage> 后台缓冲区是 Direct3D surface。  当你调用<xref:System.Windows.Interop.D3DImage.Unlock%2A>在硬件上显示的方法时, 对后台缓冲区的更改将被转发到前台缓冲区。 偶尔, 前台缓冲区变为不可用。 此缺乏可用性的原因可能是屏幕锁定、全屏独占 Direct3D 应用程序、用户切换或其他系统活动。 出现这种情况时, 将通过处理<xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>事件来通知您的 WPF 应用程序。  应用程序响应前台缓冲区变为不可用的方式取决于是否允许 WPF 回退到软件呈现。 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>方法具有一个重载, 该重载采用一个参数, 该参数指定 WPF 是否回退到软件呈现。  
  
 当调用<xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29>重载或<xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29>调用重载`enableSoftwareFallback` , 并将参数设置为`false`时, 呈现系统将在前台缓冲区变为不可用且没有任何内容时释放对后台缓冲区的引用会. 当前台缓冲区再次可用时, 呈现系统将引发<xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>事件来通知您的 WPF 应用程序。  您可以为<xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>事件创建一个事件处理程序, 以便使用有效的 Direct3D surface 再次重新开始呈现。 若要重新启动呈现, 必须<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>调用。  
  
 当调用<xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29>重载`enableSoftwareFallback`且参数设置为`true`时, 呈现系统将在前台缓冲区变为不可用时保留对后台缓冲区的引用<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> , 因此, 无需在前台缓冲区再次可用。  
  
 启用软件呈现时, 可能会出现用户的设备不可用的情况, 但呈现系统将保留对 Direct3D surface 的引用。 若要检查 Direct3D9 设备是否不可用, 请调用`TestCooperativeLevel`方法。 若要检查 Direct3D9Ex 设备, 请`CheckDeviceState`调用方法, 因为`TestCooperativeLevel`该方法已弃用, 并且始终返回 success。 如果用户设备变为不可用, 则调用<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>以释放 WPF 对后台缓冲区的引用。  如果需要重置设备, <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>请在`backBuffer`参数设置为`null`的情况下调用, 然后再次<xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> `backBuffer`调用, 并将设置为有效的 Direct3D 图面。  
  
 仅当实现多适配器支持时, 才从无效设备调用方法进行恢复。`Reset` 否则, 释放所有 Direct3D9 接口并完全重新创建它们。 如果适配器布局发生了更改, 则在更改之前创建的 Direct3D9 对象不会更新。  
  
## <a name="handling-resizing"></a>处理调整大小  
 如果以分辨率而不是本机大小显示, 则会根据当前<xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>大小进行缩放, 只不过<xref:System.Windows.Media.Effects.SamplingMode.Bilinear>会将替换为<xref:System.Windows.Media.BitmapScalingMode.Fant>。 <xref:System.Windows.Interop.D3DImage>  
  
 如果需要更高的保真度, 则当容器的<xref:System.Windows.Interop.D3DImage>大小改变时, 必须创建新的图面。  
  
 可以通过三种方法来处理调整大小。  
  
- 当大小改变时, 参与布局系统并创建一个新表面。 不要创建太多的图面, 因为您可能会耗尽或分段视频内存。  
  
- 等待, 直到有一个固定时间段的大小调整事件创建新的图面。  
  
- 创建一个<xref:System.Windows.Threading.DispatcherTimer> , 它每秒检查容器维度多次。  
  
## <a name="multi-monitor-optimization"></a>多监视器优化  
 呈现系统将移动<xref:System.Windows.Interop.D3DImage>到另一个监视器时, 可能会显著降低性能。  
  
 在 WDDM 上, 只要监视器位于同一视频卡上并且你使用`Direct3DCreate9Ex`的是, 就不会降低性能。 如果监视器位于单独的视频卡上, 则性能会降低。 在 Windows XP 上, 始终会降低性能。  
  
 <xref:System.Windows.Interop.D3DImage>当移动到另一个监视器时, 可以在相应的适配器上创建新的图面来还原良好的性能。  
  
 若要避免性能损失, 请专门为多监视器案例编写代码。 以下列表显示了一种编写多监视器代码的方法。  
  
1. 使用方法在<xref:System.Windows.Interop.D3DImage>屏幕空间中查找点。 `Visual.ProjectToScreen`  
  
2. `MonitorFromPoint`使用 GDI 方法查找正在显示该点的监视器。  
  
3. `IDirect3D9::GetAdapterMonitor`使用方法可查找监视器所处的 Direct3D9 适配器。  
  
4. 如果适配器与具有后台缓冲区的适配器不相同, 请在新监视器上创建新的后台缓冲区, 并将其分配给<xref:System.Windows.Interop.D3DImage>后台缓冲区。  
  
> [!NOTE]
> 如果跨越监视, 则除了在 WDDM 和`IDirect3D9Ex`同一适配器上的情况下, 性能会降低。 <xref:System.Windows.Interop.D3DImage> 在这种情况下, 无法提高性能。  
  
 下面的代码示例演示如何查找当前监视器。  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 当<xref:System.Windows.Interop.D3DImage>容器的大小或位置发生更改时, 更新监视器, 或`DispatcherTimer`使用每秒更新几次的来更新监视器。  
  
## <a name="wpf-software-rendering"></a>WPF 软件呈现  
 在以下情况下, WPF 在软件的 UI 线程上同步呈现。  
  
- 打印  
  
- <xref:System.Windows.Media.Effects.BitmapEffect>  
  
- <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 出现这种情况时, 呈现系统会调用<xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>方法将硬件缓冲区复制到软件。 默认实现通过您的`GetRenderTargetData`图面调用方法。 由于此调用发生在锁定/解锁模式之外, 因此可能会失败。 在这种情况下`CopyBackBuffer` , 该`null`方法将返回, 并且不会显示图像。  
  
 可以重写<xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>方法, 调用基实现, 如果返回`null`, 则可以返回占位符<xref:System.Windows.Media.Imaging.BitmapSource>。  
  
 你还可以实现自己的软件呈现, 而不是调用基实现。  
  
> [!NOTE]
> 如果 wpf 完全在软件中呈现, <xref:System.Windows.Interop.D3DImage>则不会显示, 因为 wpf 没有前台缓冲区。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.D3DImage>
- [Direct3D9 和 WPF 互操作性的性能注意事项](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [演练：创建用于在 WPF 中承载的 Direct3D9 内容](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [演练：在 WPF 中承载 Direct3D9 内容](walkthrough-hosting-direct3d9-content-in-wpf.md)
