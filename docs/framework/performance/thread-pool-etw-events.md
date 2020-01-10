---
title: 线程池 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: e1deb17dfdfea4c8b66eb8d836a10bf888727e1a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715904"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="a2051-102">线程池 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a2051-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="a2051-103">这些事件收集有关工作线程和 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="a2051-104">存在两组线程池事件：</span><span class="sxs-lookup"><span data-stu-id="a2051-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="a2051-105">[工作线程池事件](#worker-thread-pool-events)：提供有关应用程序如何使用线程池以及工作负荷如何影响并发控制的信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="a2051-106">[I/O 线程池事件](#io-thread-events)：提供有关线程池中创建、停用、恢复或终止的 I/O 线程的信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="a2051-107">工作线程池事件</span><span class="sxs-lookup"><span data-stu-id="a2051-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="a2051-108">这些事件与运行时工作线程池相关，并提供有关线程事件的通知（例如，创建或停止线程时）。</span><span class="sxs-lookup"><span data-stu-id="a2051-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="a2051-109">工作线程池使用自适应算法进行并发控制，其中的线程数基于测得的吞吐量来计算。</span><span class="sxs-lookup"><span data-stu-id="a2051-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="a2051-110">工作线程池事件可用于了解应用程序如何使用线程池，以及某些工作负荷可能会对并发控制怎样的影响。</span><span class="sxs-lookup"><span data-stu-id="a2051-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="a2051-111">ThreadPoolWorkerThreadStart 和 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="a2051-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="a2051-112">下表显示这些事件的关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="a2051-113">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="a2051-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a2051-114">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-114">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-115">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-117">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-118">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-119">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-119">Event</span></span>|<span data-ttu-id="a2051-120">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-120">Event ID</span></span>|<span data-ttu-id="a2051-121">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a2051-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="a2051-122">50</span><span class="sxs-lookup"><span data-stu-id="a2051-122">50</span></span>|<span data-ttu-id="a2051-123">创建工作线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="a2051-124">51</span><span class="sxs-lookup"><span data-stu-id="a2051-124">51</span></span>|<span data-ttu-id="a2051-125">停止工作线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="a2051-126">52</span><span class="sxs-lookup"><span data-stu-id="a2051-126">52</span></span>|<span data-ttu-id="a2051-127">停用工作线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="a2051-128">53</span><span class="sxs-lookup"><span data-stu-id="a2051-128">53</span></span>|<span data-ttu-id="a2051-129">停用的工作线程再次变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="a2051-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="a2051-130">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-131">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-131">Field name</span></span>|<span data-ttu-id="a2051-132">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-132">Data type</span></span>|<span data-ttu-id="a2051-133">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="a2051-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="a2051-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2051-135">win:UInt32</span></span>|<span data-ttu-id="a2051-136">可用于处理工作的工作线程数，包括已在处理工作的工作线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="a2051-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="a2051-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="a2051-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2051-138">win:UInt32</span></span>|<span data-ttu-id="a2051-139">不能用于处理工作但被保留以防之后需要更多线程的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="a2051-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-140">ClrInstanceID</span></span>|<span data-ttu-id="a2051-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-141">Win:UInt16</span></span>|<span data-ttu-id="a2051-142">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="a2051-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="a2051-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="a2051-144">这些线程池事件提供用于了解和调试线程注入（并发控制）算法行为的信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="a2051-145">这些信息由工作线程池在内部使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="a2051-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="a2051-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="a2051-147">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-148">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-148">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-149">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-151">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-152">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-153">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-153">Event</span></span>|<span data-ttu-id="a2051-154">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-154">Event ID</span></span>|<span data-ttu-id="a2051-155">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="a2051-156">54</span><span class="sxs-lookup"><span data-stu-id="a2051-156">54</span></span>|<span data-ttu-id="a2051-157">指一个示例的信息收集，即具有一定并发级别的即时吞吐量测量。</span><span class="sxs-lookup"><span data-stu-id="a2051-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="a2051-158">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-159">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-159">Field name</span></span>|<span data-ttu-id="a2051-160">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-160">Data type</span></span>|<span data-ttu-id="a2051-161">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-162">吞吐量</span><span class="sxs-lookup"><span data-stu-id="a2051-162">Throughput</span></span>|<span data-ttu-id="a2051-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-163">win:Double</span></span>|<span data-ttu-id="a2051-164">每个时间单位的完成数。</span><span class="sxs-lookup"><span data-stu-id="a2051-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="a2051-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-165">ClrInstanceID</span></span>|<span data-ttu-id="a2051-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-166">Win:UInt16</span></span>|<span data-ttu-id="a2051-167">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="a2051-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="a2051-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="a2051-169">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-170">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-170">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-171">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-173">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-174">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-175">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-175">Event</span></span>|<span data-ttu-id="a2051-176">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-176">Event ID</span></span>|<span data-ttu-id="a2051-177">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="a2051-178">55</span><span class="sxs-lookup"><span data-stu-id="a2051-178">55</span></span>|<span data-ttu-id="a2051-179">当线程注入（爬山）算法确定并发级别发生更改时，在控件中记录更改。</span><span class="sxs-lookup"><span data-stu-id="a2051-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="a2051-180">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-181">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-181">Field name</span></span>|<span data-ttu-id="a2051-182">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-182">Data type</span></span>|<span data-ttu-id="a2051-183">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="a2051-184">AverageThroughput</span></span>|<span data-ttu-id="a2051-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-185">win:Double</span></span>|<span data-ttu-id="a2051-186">测量示例的平均吞吐量。</span><span class="sxs-lookup"><span data-stu-id="a2051-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="a2051-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="a2051-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="a2051-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2051-188">win:UInt32</span></span>|<span data-ttu-id="a2051-189">新的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="a2051-190">原因</span><span class="sxs-lookup"><span data-stu-id="a2051-190">Reason</span></span>|<span data-ttu-id="a2051-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a2051-191">win:UInt32</span></span>|<span data-ttu-id="a2051-192">调整的原因。</span><span class="sxs-lookup"><span data-stu-id="a2051-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="a2051-193">0x00 - 预热。</span><span class="sxs-lookup"><span data-stu-id="a2051-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="a2051-194">0x01 - 初始化。</span><span class="sxs-lookup"><span data-stu-id="a2051-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="a2051-195">0x02 - 随机移动。</span><span class="sxs-lookup"><span data-stu-id="a2051-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="a2051-196">0x03 - 攀移。</span><span class="sxs-lookup"><span data-stu-id="a2051-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="a2051-197">0x04 - 更改点。</span><span class="sxs-lookup"><span data-stu-id="a2051-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="a2051-198">0x05 - 稳定。</span><span class="sxs-lookup"><span data-stu-id="a2051-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="a2051-199">0x06 - 匮乏。</span><span class="sxs-lookup"><span data-stu-id="a2051-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="a2051-200">0x07 - 线程已超时。</span><span class="sxs-lookup"><span data-stu-id="a2051-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="a2051-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-201">ClrInstanceID</span></span>|<span data-ttu-id="a2051-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-202">Win:UInt16</span></span>|<span data-ttu-id="a2051-203">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="a2051-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="a2051-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="a2051-205">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-206">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-206">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-207">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-209">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-210">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-211">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-211">Event</span></span>|<span data-ttu-id="a2051-212">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-212">Event ID</span></span>|<span data-ttu-id="a2051-213">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="a2051-214">56</span><span class="sxs-lookup"><span data-stu-id="a2051-214">56</span></span>|<span data-ttu-id="a2051-215">在线程池上收集数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="a2051-216">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-217">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-217">Field name</span></span>|<span data-ttu-id="a2051-218">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-218">Data type</span></span>|<span data-ttu-id="a2051-219">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-220">持续时间</span><span class="sxs-lookup"><span data-stu-id="a2051-220">Duration</span></span>|<span data-ttu-id="a2051-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-221">win:Double</span></span>|<span data-ttu-id="a2051-222">收集这些统计信息的时间量（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="a2051-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="a2051-223">吞吐量</span><span class="sxs-lookup"><span data-stu-id="a2051-223">Throughput</span></span>|<span data-ttu-id="a2051-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-224">win:Double</span></span>|<span data-ttu-id="a2051-225">在此间隔期间每秒完成的平均数量。</span><span class="sxs-lookup"><span data-stu-id="a2051-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="a2051-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="a2051-226">ThreadWave</span></span>|<span data-ttu-id="a2051-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-227">win:Double</span></span>|<span data-ttu-id="a2051-228">保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="a2051-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="a2051-229">ThroughputWave</span></span>|<span data-ttu-id="a2051-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-230">win:Double</span></span>|<span data-ttu-id="a2051-231">保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="a2051-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="a2051-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="a2051-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-233">win:Double</span></span>|<span data-ttu-id="a2051-234">保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="a2051-235">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="a2051-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="a2051-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-236">win:Double</span></span>|<span data-ttu-id="a2051-237">保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="a2051-238">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="a2051-238">ThroughputRatio</span></span>|<span data-ttu-id="a2051-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-239">win:Double</span></span>|<span data-ttu-id="a2051-240">在此间隔期间因活动工作线程计数变化导致的相对吞吐量变化。</span><span class="sxs-lookup"><span data-stu-id="a2051-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="a2051-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="a2051-241">Confidence</span></span>|<span data-ttu-id="a2051-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-242">win:Double</span></span>|<span data-ttu-id="a2051-243">ThroughputRatio 字段的有效性测量。</span><span class="sxs-lookup"><span data-stu-id="a2051-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="a2051-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="a2051-244">NewcontrolSetting</span></span>|<span data-ttu-id="a2051-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="a2051-245">win:Double</span></span>|<span data-ttu-id="a2051-246">将作为活动线程计数未来变化基线的活动工作线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="a2051-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="a2051-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="a2051-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-248">Win:UInt16</span></span>|<span data-ttu-id="a2051-249">活动线程计数的未来变化量值。</span><span class="sxs-lookup"><span data-stu-id="a2051-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="a2051-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-250">ClrInstanceID</span></span>|<span data-ttu-id="a2051-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-251">Win:UInt16</span></span>|<span data-ttu-id="a2051-252">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="a2051-253">I/O 线程事件</span><span class="sxs-lookup"><span data-stu-id="a2051-253">I/O Thread Events</span></span>  
 <span data-ttu-id="a2051-254">这些线程池事件针对 I/O 线程池（完成端口）中的线程发生，该过程是异步的。</span><span class="sxs-lookup"><span data-stu-id="a2051-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="a2051-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="a2051-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="a2051-256">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-257">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-257">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-258">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-260">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-261">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-262">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-262">Event</span></span>|<span data-ttu-id="a2051-263">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-263">Event ID</span></span>|<span data-ttu-id="a2051-264">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a2051-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="a2051-265">44</span><span class="sxs-lookup"><span data-stu-id="a2051-265">44</span></span>|<span data-ttu-id="a2051-266">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="a2051-267">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-268">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-268">Field name</span></span>|<span data-ttu-id="a2051-269">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-269">Data type</span></span>|<span data-ttu-id="a2051-270">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-271">计数</span><span class="sxs-lookup"><span data-stu-id="a2051-271">Count</span></span>|<span data-ttu-id="a2051-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-272">win:UInt64</span></span>|<span data-ttu-id="a2051-273">I/O 线程数，包括新创建的线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="a2051-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="a2051-274">NumRetired</span></span>|<span data-ttu-id="a2051-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-275">win:UInt64</span></span>|<span data-ttu-id="a2051-276">已停用的工作线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="a2051-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-277">ClrInstanceID</span></span>|<span data-ttu-id="a2051-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-278">Win:UInt16</span></span>|<span data-ttu-id="a2051-279">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="a2051-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="a2051-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="a2051-281">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-282">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-282">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-283">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-285">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-286">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-287">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-287">Event</span></span>|<span data-ttu-id="a2051-288">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-288">Event ID</span></span>|<span data-ttu-id="a2051-289">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a2051-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="a2051-290">46</span><span class="sxs-lookup"><span data-stu-id="a2051-290">46</span></span>|<span data-ttu-id="a2051-291">I/O 线程变为停用候选项。</span><span class="sxs-lookup"><span data-stu-id="a2051-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="a2051-292">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-293">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-293">Field name</span></span>|<span data-ttu-id="a2051-294">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-294">Data type</span></span>|<span data-ttu-id="a2051-295">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-296">计数</span><span class="sxs-lookup"><span data-stu-id="a2051-296">Count</span></span>|<span data-ttu-id="a2051-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-297">win:UInt64</span></span>|<span data-ttu-id="a2051-298">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="a2051-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="a2051-299">NumRetired</span></span>|<span data-ttu-id="a2051-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-300">win:UInt64</span></span>|<span data-ttu-id="a2051-301">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="a2051-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-302">ClrInstanceID</span></span>|<span data-ttu-id="a2051-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-303">Win:UInt16</span></span>|<span data-ttu-id="a2051-304">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="a2051-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="a2051-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="a2051-306">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-307">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-307">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-308">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-310">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-311">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-312">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-312">Event</span></span>|<span data-ttu-id="a2051-313">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-313">Event ID</span></span>|<span data-ttu-id="a2051-314">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a2051-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="a2051-315">47</span><span class="sxs-lookup"><span data-stu-id="a2051-315">47</span></span>|<span data-ttu-id="a2051-316">I/O 线程因在该线程变为停用候选项后的等待期间内达到 I/O 而恢复使用。</span><span class="sxs-lookup"><span data-stu-id="a2051-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="a2051-317">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-318">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-318">Field name</span></span>|<span data-ttu-id="a2051-319">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-319">Data type</span></span>|<span data-ttu-id="a2051-320">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-321">计数</span><span class="sxs-lookup"><span data-stu-id="a2051-321">Count</span></span>|<span data-ttu-id="a2051-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-322">win:UInt64</span></span>|<span data-ttu-id="a2051-323">线程池中的 I/O 线程数，包括这一个。</span><span class="sxs-lookup"><span data-stu-id="a2051-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="a2051-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="a2051-324">NumRetired</span></span>|<span data-ttu-id="a2051-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-325">win:UInt64</span></span>|<span data-ttu-id="a2051-326">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="a2051-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-327">ClrInstanceID</span></span>|<span data-ttu-id="a2051-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-328">Win:UInt16</span></span>|<span data-ttu-id="a2051-329">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="a2051-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="a2051-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="a2051-331">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="a2051-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a2051-332">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="a2051-332">Keyword for raising the event</span></span>|<span data-ttu-id="a2051-333">Level</span><span class="sxs-lookup"><span data-stu-id="a2051-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a2051-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a2051-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a2051-335">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="a2051-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="a2051-336">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="a2051-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a2051-337">Event</span><span class="sxs-lookup"><span data-stu-id="a2051-337">Event</span></span>|<span data-ttu-id="a2051-338">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2051-338">Event ID</span></span>|<span data-ttu-id="a2051-339">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="a2051-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="a2051-340">45</span><span class="sxs-lookup"><span data-stu-id="a2051-340">45</span></span>|<span data-ttu-id="a2051-341">在线程池中创建 I/O 线程。</span><span class="sxs-lookup"><span data-stu-id="a2051-341">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="a2051-342">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="a2051-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a2051-343">字段名</span><span class="sxs-lookup"><span data-stu-id="a2051-343">Field name</span></span>|<span data-ttu-id="a2051-344">数据类型</span><span class="sxs-lookup"><span data-stu-id="a2051-344">Data type</span></span>|<span data-ttu-id="a2051-345">描述</span><span class="sxs-lookup"><span data-stu-id="a2051-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a2051-346">计数</span><span class="sxs-lookup"><span data-stu-id="a2051-346">Count</span></span>|<span data-ttu-id="a2051-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-347">win:UInt64</span></span>|<span data-ttu-id="a2051-348">线程池中剩余的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="a2051-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="a2051-349">NumRetired</span></span>|<span data-ttu-id="a2051-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a2051-350">win:UInt64</span></span>|<span data-ttu-id="a2051-351">已停用的 I/O 线程数。</span><span class="sxs-lookup"><span data-stu-id="a2051-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="a2051-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a2051-352">ClrInstanceID</span></span>|<span data-ttu-id="a2051-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a2051-353">Win:UInt16</span></span>|<span data-ttu-id="a2051-354">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a2051-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2051-355">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2051-355">See also</span></span>

- [<span data-ttu-id="a2051-356">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="a2051-356">CLR ETW Events</span></span>](clr-etw-events.md)
