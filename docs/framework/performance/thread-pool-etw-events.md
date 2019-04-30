---
title: 线程池 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caacee591c4df8389cea241916618f50da56b22b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949157"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="570ce-102">线程池 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="570ce-102">Thread Pool ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="570ce-103">这些事件收集有关工作线程和 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="570ce-104">存在两组线程池事件：</span><span class="sxs-lookup"><span data-stu-id="570ce-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="570ce-105">[工作线程池事件](#worker)：提供有关应用程序如何使用线程池以及工作负荷如何影响并发控制的信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-105">[Worker thread pool events](#worker), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="570ce-106">[I/O 线程池事件](#io)：提供有关线程池中创建、停用、恢复或终止的 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-106">[I/O thread pool events](#io), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  
  
<a name="worker"></a>   
## <a name="worker-thread-pool-events"></a><span data-ttu-id="570ce-107">工作线程池事件</span><span class="sxs-lookup"><span data-stu-id="570ce-107">Worker Thread Pool Events</span></span>  
 <span data-ttu-id="570ce-108">这些事件与运行时工作线程池相关，并提供有关线程事件的通知（例如，创建或停止线程时）。</span><span class="sxs-lookup"><span data-stu-id="570ce-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="570ce-109">工作线程池使用自适应算法进行并发控制，其中的线程数基于测得的吞吐量来计算。</span><span class="sxs-lookup"><span data-stu-id="570ce-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="570ce-110">工作线程池事件可用于了解应用程序如何使用线程池，以及某些工作负荷可能会对并发控制怎样的影响。</span><span class="sxs-lookup"><span data-stu-id="570ce-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="570ce-111">ThreadPoolWorkerThreadStart 和 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="570ce-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="570ce-112">下表显示这些事件的关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="570ce-113">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="570ce-113">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="570ce-114">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-114">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-115">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-117">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-118">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-119">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-119">Event</span></span>|<span data-ttu-id="570ce-120">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-120">Event ID</span></span>|<span data-ttu-id="570ce-121">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="570ce-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="570ce-122">50</span><span class="sxs-lookup"><span data-stu-id="570ce-122">50</span></span>|<span data-ttu-id="570ce-123">创建工作线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="570ce-124">51</span><span class="sxs-lookup"><span data-stu-id="570ce-124">51</span></span>|<span data-ttu-id="570ce-125">停止工作线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="570ce-126">52</span><span class="sxs-lookup"><span data-stu-id="570ce-126">52</span></span>|<span data-ttu-id="570ce-127">停用工作线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="570ce-128">53</span><span class="sxs-lookup"><span data-stu-id="570ce-128">53</span></span>|<span data-ttu-id="570ce-129">停用的工作线程再次变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="570ce-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="570ce-130">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-131">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-131">Field name</span></span>|<span data-ttu-id="570ce-132">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-132">Data type</span></span>|<span data-ttu-id="570ce-133">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="570ce-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="570ce-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="570ce-135">win:UInt32</span></span>|<span data-ttu-id="570ce-136">可用于处理工作的工作线程数，包括已在处理工作的工作线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="570ce-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="570ce-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="570ce-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="570ce-138">win:UInt32</span></span>|<span data-ttu-id="570ce-139">不能用于处理工作但被保留以防之后需要更多线程的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="570ce-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-140">ClrInstanceID</span></span>|<span data-ttu-id="570ce-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-141">Win:UInt16</span></span>|<span data-ttu-id="570ce-142">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="570ce-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="570ce-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="570ce-144">这些线程池事件提供用于了解和调试线程注入（并发控制）算法行为的信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="570ce-145">这些信息由工作线程池在内部使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="570ce-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="570ce-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="570ce-147">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-148">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-148">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-149">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-151">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-152">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-153">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-153">Event</span></span>|<span data-ttu-id="570ce-154">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-154">Event ID</span></span>|<span data-ttu-id="570ce-155">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="570ce-156">54</span><span class="sxs-lookup"><span data-stu-id="570ce-156">54</span></span>|<span data-ttu-id="570ce-157">指一个示例的信息收集，即具有一定并发级别的即时吞吐量测量。</span><span class="sxs-lookup"><span data-stu-id="570ce-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="570ce-158">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-159">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-159">Field name</span></span>|<span data-ttu-id="570ce-160">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-160">Data type</span></span>|<span data-ttu-id="570ce-161">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-162">吞吐量</span><span class="sxs-lookup"><span data-stu-id="570ce-162">Throughput</span></span>|<span data-ttu-id="570ce-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-163">win:Double</span></span>|<span data-ttu-id="570ce-164">每个时间单位的完成数。</span><span class="sxs-lookup"><span data-stu-id="570ce-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="570ce-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-165">ClrInstanceID</span></span>|<span data-ttu-id="570ce-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-166">Win:UInt16</span></span>|<span data-ttu-id="570ce-167">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="570ce-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="570ce-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="570ce-169">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-170">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-170">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-171">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-173">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-174">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-175">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-175">Event</span></span>|<span data-ttu-id="570ce-176">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-176">Event ID</span></span>|<span data-ttu-id="570ce-177">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="570ce-178">55</span><span class="sxs-lookup"><span data-stu-id="570ce-178">55</span></span>|<span data-ttu-id="570ce-179">当线程注入（爬山）算法确定并发级别发生更改时，在控件中记录更改。</span><span class="sxs-lookup"><span data-stu-id="570ce-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="570ce-180">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-181">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-181">Field name</span></span>|<span data-ttu-id="570ce-182">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-182">Data type</span></span>|<span data-ttu-id="570ce-183">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="570ce-184">AverageThroughput</span></span>|<span data-ttu-id="570ce-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-185">win:Double</span></span>|<span data-ttu-id="570ce-186">测量示例的平均吞吐量。</span><span class="sxs-lookup"><span data-stu-id="570ce-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="570ce-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="570ce-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="570ce-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="570ce-188">win:UInt32</span></span>|<span data-ttu-id="570ce-189">新的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="570ce-190">原因</span><span class="sxs-lookup"><span data-stu-id="570ce-190">Reason</span></span>|<span data-ttu-id="570ce-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="570ce-191">win:UInt32</span></span>|<span data-ttu-id="570ce-192">调整的原因。</span><span class="sxs-lookup"><span data-stu-id="570ce-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="570ce-193">0x00 - 预热。</span><span class="sxs-lookup"><span data-stu-id="570ce-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="570ce-194">0x01 - 初始化。</span><span class="sxs-lookup"><span data-stu-id="570ce-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="570ce-195">0x02 - 随机移动。</span><span class="sxs-lookup"><span data-stu-id="570ce-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="570ce-196">0x03 - 攀移。</span><span class="sxs-lookup"><span data-stu-id="570ce-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="570ce-197">0x04 - 更改点。</span><span class="sxs-lookup"><span data-stu-id="570ce-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="570ce-198">0x05 - 稳定。</span><span class="sxs-lookup"><span data-stu-id="570ce-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="570ce-199">0x06 - 匮乏。</span><span class="sxs-lookup"><span data-stu-id="570ce-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="570ce-200">0x07 - 线程已超时。</span><span class="sxs-lookup"><span data-stu-id="570ce-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="570ce-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-201">ClrInstanceID</span></span>|<span data-ttu-id="570ce-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-202">Win:UInt16</span></span>|<span data-ttu-id="570ce-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="570ce-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="570ce-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="570ce-205">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-206">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-206">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-207">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-209">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-210">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-211">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-211">Event</span></span>|<span data-ttu-id="570ce-212">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-212">Event ID</span></span>|<span data-ttu-id="570ce-213">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="570ce-214">56</span><span class="sxs-lookup"><span data-stu-id="570ce-214">56</span></span>|<span data-ttu-id="570ce-215">在线程池上收集数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="570ce-216">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-217">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-217">Field name</span></span>|<span data-ttu-id="570ce-218">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-218">Data type</span></span>|<span data-ttu-id="570ce-219">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-220">持续时间</span><span class="sxs-lookup"><span data-stu-id="570ce-220">Duration</span></span>|<span data-ttu-id="570ce-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-221">win:Double</span></span>|<span data-ttu-id="570ce-222">收集这些统计信息的时间量（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="570ce-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="570ce-223">吞吐量</span><span class="sxs-lookup"><span data-stu-id="570ce-223">Throughput</span></span>|<span data-ttu-id="570ce-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-224">win:Double</span></span>|<span data-ttu-id="570ce-225">在此间隔期间每秒完成的平均数量。</span><span class="sxs-lookup"><span data-stu-id="570ce-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="570ce-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="570ce-226">ThreadWave</span></span>|<span data-ttu-id="570ce-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-227">win:Double</span></span>|<span data-ttu-id="570ce-228">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="570ce-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="570ce-229">ThroughputWave</span></span>|<span data-ttu-id="570ce-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-230">win:Double</span></span>|<span data-ttu-id="570ce-231">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="570ce-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="570ce-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="570ce-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-233">win:Double</span></span>|<span data-ttu-id="570ce-234">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="570ce-235">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="570ce-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="570ce-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-236">win:Double</span></span>|<span data-ttu-id="570ce-237">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="570ce-238">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="570ce-238">ThroughputRatio</span></span>|<span data-ttu-id="570ce-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-239">win:Double</span></span>|<span data-ttu-id="570ce-240">在此间隔期间因活动工作线程计数变化导致的相对吞吐量变化。</span><span class="sxs-lookup"><span data-stu-id="570ce-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="570ce-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="570ce-241">Confidence</span></span>|<span data-ttu-id="570ce-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-242">win:Double</span></span>|<span data-ttu-id="570ce-243">ThroughputRatio 字段的有效性测量。</span><span class="sxs-lookup"><span data-stu-id="570ce-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="570ce-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="570ce-244">NewcontrolSetting</span></span>|<span data-ttu-id="570ce-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="570ce-245">win:Double</span></span>|<span data-ttu-id="570ce-246">将作为活动线程计数未来变化基线的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="570ce-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="570ce-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="570ce-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-248">Win:UInt16</span></span>|<span data-ttu-id="570ce-249">活动线程计数的未来变化量值。</span><span class="sxs-lookup"><span data-stu-id="570ce-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="570ce-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-250">ClrInstanceID</span></span>|<span data-ttu-id="570ce-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-251">Win:UInt16</span></span>|<span data-ttu-id="570ce-252">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="570ce-253">返回页首</span><span class="sxs-lookup"><span data-stu-id="570ce-253">Back to top</span></span>](#top)  
  
<a name="io"></a>   
## <a name="io-thread-events"></a><span data-ttu-id="570ce-254">I/O 线程事件</span><span class="sxs-lookup"><span data-stu-id="570ce-254">I/O Thread Events</span></span>  
 <span data-ttu-id="570ce-255">这些线程池事件针对 I/O 线程池（完成端口）中的线程发生，该过程是异步的。</span><span class="sxs-lookup"><span data-stu-id="570ce-255">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreatev1"></a><span data-ttu-id="570ce-256">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="570ce-256">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="570ce-257">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-257">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-258">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-258">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-259">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-259">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-260">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-260">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-261">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-261">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-262">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-262">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-263">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-263">Event</span></span>|<span data-ttu-id="570ce-264">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-264">Event ID</span></span>|<span data-ttu-id="570ce-265">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="570ce-265">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="570ce-266">44</span><span class="sxs-lookup"><span data-stu-id="570ce-266">44</span></span>|<span data-ttu-id="570ce-267">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-267">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="570ce-268">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-268">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-269">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-269">Field name</span></span>|<span data-ttu-id="570ce-270">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-270">Data type</span></span>|<span data-ttu-id="570ce-271">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-271">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-272">计数</span><span class="sxs-lookup"><span data-stu-id="570ce-272">Count</span></span>|<span data-ttu-id="570ce-273">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-273">win:UInt64</span></span>|<span data-ttu-id="570ce-274">I/O 线程数，包括新创建的线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-274">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="570ce-275">NumRetired</span><span class="sxs-lookup"><span data-stu-id="570ce-275">NumRetired</span></span>|<span data-ttu-id="570ce-276">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-276">win:UInt64</span></span>|<span data-ttu-id="570ce-277">已停用的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-277">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="570ce-278">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-278">ClrInstanceID</span></span>|<span data-ttu-id="570ce-279">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-279">Win:UInt16</span></span>|<span data-ttu-id="570ce-280">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretirev1"></a><span data-ttu-id="570ce-281">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="570ce-281">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="570ce-282">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-282">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-283">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-283">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-284">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-284">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-286">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-286">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-287">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-287">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-288">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-288">Event</span></span>|<span data-ttu-id="570ce-289">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-289">Event ID</span></span>|<span data-ttu-id="570ce-290">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="570ce-290">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="570ce-291">46</span><span class="sxs-lookup"><span data-stu-id="570ce-291">46</span></span>|<span data-ttu-id="570ce-292">I/O 线程变为停用候选项。</span><span class="sxs-lookup"><span data-stu-id="570ce-292">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="570ce-293">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-293">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-294">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-294">Field name</span></span>|<span data-ttu-id="570ce-295">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-295">Data type</span></span>|<span data-ttu-id="570ce-296">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-296">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-297">计数</span><span class="sxs-lookup"><span data-stu-id="570ce-297">Count</span></span>|<span data-ttu-id="570ce-298">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-298">win:UInt64</span></span>|<span data-ttu-id="570ce-299">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-299">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="570ce-300">NumRetired</span><span class="sxs-lookup"><span data-stu-id="570ce-300">NumRetired</span></span>|<span data-ttu-id="570ce-301">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-301">win:UInt64</span></span>|<span data-ttu-id="570ce-302">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-302">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="570ce-303">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-303">ClrInstanceID</span></span>|<span data-ttu-id="570ce-304">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-304">Win:UInt16</span></span>|<span data-ttu-id="570ce-305">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-305">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretirev1"></a><span data-ttu-id="570ce-306">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="570ce-306">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="570ce-307">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-307">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-308">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-308">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-309">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-309">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-310">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-310">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-311">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-311">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-312">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-312">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-313">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-313">Event</span></span>|<span data-ttu-id="570ce-314">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-314">Event ID</span></span>|<span data-ttu-id="570ce-315">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="570ce-315">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="570ce-316">47</span><span class="sxs-lookup"><span data-stu-id="570ce-316">47</span></span>|<span data-ttu-id="570ce-317">I/O 线程因在该线程变为停用候选项后的等待期间内达到 I/O 而恢复使用。</span><span class="sxs-lookup"><span data-stu-id="570ce-317">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="570ce-318">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-318">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-319">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-319">Field name</span></span>|<span data-ttu-id="570ce-320">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-320">Data type</span></span>|<span data-ttu-id="570ce-321">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-321">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-322">计数</span><span class="sxs-lookup"><span data-stu-id="570ce-322">Count</span></span>|<span data-ttu-id="570ce-323">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-323">win:UInt64</span></span>|<span data-ttu-id="570ce-324">线程池中的 I/O 线程数，包括这一个。</span><span class="sxs-lookup"><span data-stu-id="570ce-324">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="570ce-325">NumRetired</span><span class="sxs-lookup"><span data-stu-id="570ce-325">NumRetired</span></span>|<span data-ttu-id="570ce-326">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-326">win:UInt64</span></span>|<span data-ttu-id="570ce-327">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-327">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="570ce-328">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-328">ClrInstanceID</span></span>|<span data-ttu-id="570ce-329">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-329">Win:UInt16</span></span>|<span data-ttu-id="570ce-330">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-330">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="570ce-331">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="570ce-331">IOThreadTerminate</span></span>  
 <span data-ttu-id="570ce-332">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="570ce-332">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="570ce-333">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="570ce-333">Keyword for raising the event</span></span>|<span data-ttu-id="570ce-334">级别</span><span class="sxs-lookup"><span data-stu-id="570ce-334">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="570ce-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="570ce-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="570ce-336">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="570ce-336">Informational (4)</span></span>|  
  
 <span data-ttu-id="570ce-337">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="570ce-337">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="570ce-338">Event</span><span class="sxs-lookup"><span data-stu-id="570ce-338">Event</span></span>|<span data-ttu-id="570ce-339">事件 ID</span><span class="sxs-lookup"><span data-stu-id="570ce-339">Event ID</span></span>|<span data-ttu-id="570ce-340">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="570ce-340">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="570ce-341">45</span><span class="sxs-lookup"><span data-stu-id="570ce-341">45</span></span>|<span data-ttu-id="570ce-342">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="570ce-342">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="570ce-343">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="570ce-343">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="570ce-344">字段名</span><span class="sxs-lookup"><span data-stu-id="570ce-344">Field name</span></span>|<span data-ttu-id="570ce-345">数据类型</span><span class="sxs-lookup"><span data-stu-id="570ce-345">Data type</span></span>|<span data-ttu-id="570ce-346">描述</span><span class="sxs-lookup"><span data-stu-id="570ce-346">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="570ce-347">计数</span><span class="sxs-lookup"><span data-stu-id="570ce-347">Count</span></span>|<span data-ttu-id="570ce-348">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-348">win:UInt64</span></span>|<span data-ttu-id="570ce-349">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-349">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="570ce-350">NumRetired</span><span class="sxs-lookup"><span data-stu-id="570ce-350">NumRetired</span></span>|<span data-ttu-id="570ce-351">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="570ce-351">win:UInt64</span></span>|<span data-ttu-id="570ce-352">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="570ce-352">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="570ce-353">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="570ce-353">ClrInstanceID</span></span>|<span data-ttu-id="570ce-354">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="570ce-354">Win:UInt16</span></span>|<span data-ttu-id="570ce-355">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="570ce-355">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="570ce-356">请参阅</span><span class="sxs-lookup"><span data-stu-id="570ce-356">See also</span></span>

- [<span data-ttu-id="570ce-357">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="570ce-357">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
