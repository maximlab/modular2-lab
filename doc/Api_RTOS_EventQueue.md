## EventQueue
<div align=center><img src="https://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.png">

EventQueue 类层次结构</div>                                                           
EventQueue 类为调度事件提供了灵活的队列。您可以使用 EventQueue 类在多个线程之间进行同步，或者将事件移出中断上下文（延迟执行耗时或非 ISR 安全操作）。

EventQueue 类是线程和 ISR 安全的。

您可以使用 dispatch 和 dispatch_forever API 来执行挂起事件。break_dispatch 用于终止指定 EventQueue 中事件的执行。

## 共享事件队列
Mbed OS 提供了两个软件可以使用的共享队列。这可以避免创建私有事件分派线程并减少使用的 RAM 总量的需要。

## EventQueue 类参考
[events::EventQueue 类参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html)
<table><tbody><tr><td colspan="2">数据结构</td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context00.html" rel="nofollow" target="_blank">context00</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context01.html" rel="nofollow" target="_blank">context01</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context02.html" rel="nofollow" target="_blank">context02</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context03.html" rel="nofollow" target="_blank">context03</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context04.html" rel="nofollow" target="_blank">context04</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context05.html" rel="nofollow" target="_blank">context05</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context10.html" rel="nofollow" target="_blank">context10</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context11.html" rel="nofollow" target="_blank">context11</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context12.html" rel="nofollow" target="_blank">context12</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context13.html" rel="nofollow" target="_blank">context13</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context14.html" rel="nofollow" target="_blank">context14</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context15.html" rel="nofollow" target="_blank">context15</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context20.html" rel="nofollow" target="_blank">context20</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context21.html" rel="nofollow" target="_blank">context21</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context22.html" rel="nofollow" target="_blank">context22</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context23.html" rel="nofollow" target="_blank">context23</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context24.html" rel="nofollow" target="_blank">context24</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context25.html" rel="nofollow" target="_blank">context25</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context30.html" rel="nofollow" target="_blank">context30</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context31.html" rel="nofollow" target="_blank">context31</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context32.html" rel="nofollow" target="_blank">context32</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context33.html" rel="nofollow" target="_blank">context33</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context34.html" rel="nofollow" target="_blank">context34</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context35.html" rel="nofollow" target="_blank">context35</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context40.html" rel="nofollow" target="_blank">context40</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context41.html" rel="nofollow" target="_blank">context41</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context42.html" rel="nofollow" target="_blank">context42</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context43.html" rel="nofollow" target="_blank">context43</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context44.html" rel="nofollow" target="_blank">context44</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context45.html" rel="nofollow" target="_blank">context45</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context50.html" rel="nofollow" target="_blank">context50</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context51.html" rel="nofollow" target="_blank">context51</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context52.html" rel="nofollow" target="_blank">context52</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context53.html" rel="nofollow" target="_blank">context53</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context54.html" rel="nofollow" target="_blank">context54</a></td>
		</tr><tr><td style="vertical-align:top;">struct &nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structevents_1_1_event_queue_1_1context55.html" rel="nofollow" target="_blank">context55</a></td>
		</tr></tbody></table>
<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7a3489cec34e02315305987f6fde0670" rel="nofollow" target="_blank">EventQueue</a> (unsigned size=(32 *((sizeof(struct <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structequeue__event.html" rel="nofollow" target="_blank">equeue_event</a>)+2 *sizeof(void *))-2 *sizeof(void *)+sizeof(<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void()&gt;))), unsigned char *buffer=NULL)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a0df38ea9760af7d56e9f80b45136cc58" rel="nofollow" target="_blank">~EventQueue</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae3ea160605a42a37745ac7f23bc6cfe9" rel="nofollow" target="_blank">dispatch</a> (int ms=-1)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aec90ac04212388b098d3dc622a34863b" rel="nofollow" target="_blank">dispatch_forever</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a376481aceeac4671b95376530e1b02ed" rel="nofollow" target="_blank">break_dispatch</a> ()</td>
		</tr><tr><td style="vertical-align:top;">unsigned&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a941a9361216fa65d04984a0699dce8d8" rel="nofollow" target="_blank">tick</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a1a2c9f5b84cde2e381acb2ba830faaa0" rel="nofollow" target="_blank">cancel</a> (int id)</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a5343b911438379a7d4e8db126feff0a0" rel="nofollow" target="_blank">time_left</a> (int id)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a4efaf080d8ce3c75310649bd8ade4b3a" rel="nofollow" target="_blank">background</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(int)&gt; update)</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a2a05f85dbf893b9d72657fa629ccf79d" rel="nofollow" target="_blank">chain</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html" rel="nofollow" target="_blank">EventQueue</a> *target)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a72bca83df9c1c36b97497892c839b7bf" rel="nofollow" target="_blank">call</a> (F f)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a71bb0088bde9491bf3577ba27606b2ce" rel="nofollow" target="_blank">call</a> (F f, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae1e82fb2a16d764ed787d3581136b4d3" rel="nofollow" target="_blank">call</a> (F f, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ac5e8fccfe9bd06eff675b7f26305427d" rel="nofollow" target="_blank">call</a> (F f, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a43f32c7fd331f54a8f305f85c3763bb4" rel="nofollow" target="_blank">call</a> (F f, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aad6a288ce22c48a3bf64c2509d5e6498" rel="nofollow" target="_blank">call</a> (F f, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a0880f53a67c304c609c8e934b7e8cc05" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)())</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ad9e9223ac1e41937f1feb10be25c4f52" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)() const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#addd58389e39c3e2b924f7e320b8b3f13" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)() volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a9f53cbaa57f3bf63bc704dde596783d4" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)() const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a656df948592e246ba96c27907412da0f" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)(A0), A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#af0c7efe1bed33ba5b6de9eef3a1a9921" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)(A0) const, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8559c19864387d23198df8d929121a94" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)(A0) volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a9b00e0357dd39528aff86cf0cf45ddc8" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)(A0) const volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a50bb8a932a5bd708ce4fed14b4e369fc" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)(A0, A1), A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a3f9ff012761722fbca73ab019ab9f814" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)(A0, A1) const, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a4d2ee97cdb75659df28545d2f82a0b7c" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)(A0, A1) volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aabfe7b684f3c8258735db51ee6240c41" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)(A0, A1) const volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a5a3a9e3b9001e55edd52516c1fd1abcd" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)(A0, A1, A2), A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a945ab47802f527569a04e8afb5c78c55" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)(A0, A1, A2) const, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ab136f0c08484f535fba27d24cb5ec927" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)(A0, A1, A2) volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a0256b745835f329c6f7365141d540a59" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)(A0, A1, A2) const volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a9b6140a9cd98254ff3a283e011272c13" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)(A0, A1, A2, A3), A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ac029b53db9abce15eed39e27a32afecb" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)(A0, A1, A2, A3) const, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a885d23c235b36dfa0e043526fa3059eb" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)(A0, A1, A2, A3) volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a1bf13b6036dd2fe9e6f3bebacbfa2967" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)(A0, A1, A2, A3) const volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aa2e5d02dd1b19aae2fa02c57682c2b49" rel="nofollow" target="_blank">call</a> (T *obj, R(T::*method)(A0, A1, A2, A3, A4), A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#af35a062b883171bb6830a628bed51254" rel="nofollow" target="_blank">call</a> (const T *obj, R(T::*method)(A0, A1, A2, A3, A4) const, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a20f2dfe69b28781975636fdfa8156b62" rel="nofollow" target="_blank">call</a> (volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a68953617c221444ea592cb9aa3effb8f" rel="nofollow" target="_blank">call</a> (const volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a16a19896ea4f18cef3f7dbb7ed30078a" rel="nofollow" target="_blank">call_in</a> (int ms, F f)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a88a4c1f414fc49378cc98e2645955902" rel="nofollow" target="_blank">call_in</a> (int ms, F f, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a447f6961a7e83fc8903b5d53d70026fb" rel="nofollow" target="_blank">call_in</a> (int ms, F f, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aa8544b574e03525d6ae97cf536e8b5fc" rel="nofollow" target="_blank">call_in</a> (int ms, F f, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a6e0fe8deca294e06b9c6302b48e53ad3" rel="nofollow" target="_blank">call_in</a> (int ms, F f, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a5b6678a48ba98131a52884e81e880ba9" rel="nofollow" target="_blank">call_in</a> (int ms, F f, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8360d9be61b23984390199f0340f0bd0" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)())</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a71adabdda4dbd5707be1752496aaf0b9" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)() const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8e2a43c77ce812d9d54c3abb9240c41d" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)() volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a9c707dc72fe9b09c67fd8438a427dad8" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)() const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a50818053e0eaa2c0b02d551a70228a4d" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)(A0), A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a05e80aee0f28c1063649cd3aeb69de96" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)(A0) const, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aba840331342c99ba00512c66c857c105" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)(A0) volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae5d48bddcf20f5049d30b4eb32f5ecba" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)(A0) const volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae5560eea855be2dc94165002799899d3" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)(A0, A1), A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aefe1abaacc76bf4efa7fd03e3652dda6" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)(A0, A1) const, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ac640310475eebf144fdb40fca3c2c91e" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)(A0, A1) volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aab42c5a1fd9e5e6ffdf866fcdc4194ef" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1) const volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a3e97b0f9f647f0d4737f0e475ad0278c" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)(A0, A1, A2), A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7aac6ad727520380a51045497487f4a6" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2) const, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a467375be920e62c1097a54612491da34" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2) volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7f0497ace92fa78bfe4dc64afacab989" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2) const volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a3022ec69d5ab03cd8bcfdb6d8e642270" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)(A0, A1, A2, A3), A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8889f6bb4df1f7356d12a2333fe344e0" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2, A3) const, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aed685249a6a1af90f99f7aab5151cde3" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2, A3) volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a18b8c9d08ffdc3a00a8de8351f1be08c" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2, A3) const volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a92ac8521203f475789133214507cff39" rel="nofollow" target="_blank">call_in</a> (int ms, T *obj, R(T::*method)(A0, A1, A2, A3, A4), A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a900d360fad146941da28936559f6938c" rel="nofollow" target="_blank">call_in</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2, A3, A4) const, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a844d35d5eb95d995b29ed140859e678c" rel="nofollow" target="_blank">call_in</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#af42391112b69d76c6625cdf64452281d" rel="nofollow" target="_blank">call_in</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a93a6903ade6d3762e4c32bb47063cf04" rel="nofollow" target="_blank">call_every</a> (int ms, F f)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae2edd53b4d12ab3f01a3c9bda58310f0" rel="nofollow" target="_blank">call_every</a> (int ms, F f, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ace88d6282fecdf7a3451a54ff8ee492e" rel="nofollow" target="_blank">call_every</a> (int ms, F f, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a6eb2476bbd61769f988e7339209cb258" rel="nofollow" target="_blank">call_every</a> (int ms, F f, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8107f297313fd55ff305b9576e8d7c92" rel="nofollow" target="_blank">call_every</a> (int ms, F f, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename F , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a8973db2abba5c96392bf85a8c3534238" rel="nofollow" target="_blank">call_every</a> (int ms, F f, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7a5c77152602058471476f56862e702f" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)())</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aeab5ad0a86b2411d5d2aeb9089845c13" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)() const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a73e92a508178350a73b3e6ed25fa9a44" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)() volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#acf4f5c7a141fd0eeb33b782407ba22f0" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)() const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae600d48e2b7811a6cd31f26eef0365b2" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)(A0), A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#abdee916ada139a3a897e300ccdc120bc" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)(A0) const, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ae6fb9dbbcfa10a099f51d9588817bab5" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)(A0) volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#abdb81e780f30a88d66d31363339ff7ff" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)(A0) const volatile, A0 a0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ab4574463218337f4092064c9bf86bcd7" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)(A0, A1), A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a15438fb8cd770ad684fd291e779e7437" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)(A0, A1) const, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a415c8c60ad1daf04b8da3f39424041f7" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)(A0, A1) volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7067f82241937f5234a93d8223cbf774" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1) const volatile, A0 a0, A1 a1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#afdb5db55b17b92a93d53bc40f12388f0" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)(A0, A1, A2), A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a92e5e6ec0256b40ef77a261803912cd7" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2) const, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a91a8b18a53cf237387a4c3429037823f" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2) volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a3575d6767357d663871d98e451f970e5" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2) const volatile, A0 a0, A1 a1, A2 a2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a622bf7579e548780f4b9b3b65cb8f717" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)(A0, A1, A2, A3), A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a993a8134868e822cd7b94a0e0efdbab6" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2, A3) const, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a1635afd1d99200a77b53a7011c7a53a1" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2, A3) volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a42b3dedd68d902e72bf554cf4384ec6d" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2, A3) const volatile, A0 a0, A1 a1, A2 a2, A3 a3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#ab6714a8fc7f2b554d492b542443c7141" rel="nofollow" target="_blank">call_every</a> (int ms, T *obj, R(T::*method)(A0, A1, A2, A3, A4), A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a7b972b374c6a110230e3d95b9132f6f2" rel="nofollow" target="_blank">call_every</a> (int ms, const T *obj, R(T::*method)(A0, A1, A2, A3, A4) const, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#a212a7961f2a53100a0b085bcb0860069" rel="nofollow" target="_blank">call_every</a> (int ms, volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;">int&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event_queue.html#aab483d86f4859432954aa69e5b735ba4" rel="nofollow" target="_blank">call_every</a> (int ms, const volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile, A0 a0, A1 a1, A2 a2, A3 a3, A4 a4)</td>
		</tr><tr><td colspan="2">template&lt;typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7de154ab93031e4dac9923cb3da14b0c" rel="nofollow" target="_blank">event</a> (R(*func)())</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0e4b89ce7fc6d8fb85b8a0ec6d8b0231" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)())</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad62c10319d4276b1b3ffa1a65440d53e" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)() const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5850d70d36e5c3b9d4f5862f4bc08955" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)() volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1c3157d828583c24c6bc16ff93a35190" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)() const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga122bcdf1b52d89b93cd582fe3d4b429f" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R()&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga316b7dc4562d27faa1a54f71069fe0e9" rel="nofollow" target="_blank">event</a> (R(*func)(B0), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8fc831f05a7977d915e2b58f62f8c835" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga87306621f8e39f18e202e6268aef18ca" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa0f4028d94f8e2ecc8c6f626acc25453" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8df1b64e974c08979e3ab06a9a3b69a1" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gafcd65284e7abcca9b7e59be5cd341d76" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga17dfbe4a585339c0445a1ea13c629e28" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga313cc22d1f0b6de48febef0c41e9b8ea" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaca827c218f49fa62b4c12b6bb19875e8" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga57e4be734bb205aecd3cecd02e6208db" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad0df0a866a3a1e3c3cd0d3fd773efe72" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4ca15c8010722b7283807c24bb46efeb" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga6dafdaf63a1a12be25ace241cdfb661b" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8d04e3e950b636810ba17ac0e332170a" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1210946f7459031b6090aa6351c75c23" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8d37c2de092b1a4a65d3b819690884bf" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5c283bf3d1ddcc42294bba9cfbde5cf9" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4466a0b4e63a24efd04f272973992939" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab6637690fb719d9e3dd00c9178f9fd5f" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4e6692726b87a7f1e6d100379af95088" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga473be1aa62782b24fa529db525491ef3" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga2bbd4f1b186c99c15b676d7c743f9b74" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga78a94d6b01da9db1d5c7cb2b5113d1fd" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5711387fc50e9f2b61db898382accf61" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga50d5772422d6a3b3e285e9bd6587eb33" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga520fb0e86a64781fede7d06183537e3f" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga2186eb045093f2375978a349068ad964" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga36e2458e60b82289c1f71ae1c7d98719" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga66c90b7a85aa74553714c5729b4f547e" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void()&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga95345d9c9b73a90c5abc4e6d528bdf2e" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaee8505176308d8eeb34b52d0d0ab5fc9" rel="nofollow" target="_blank">event</a> (R(*func)(A0))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gae665e0cf76c33340f51d1f7579f4acaf" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(A0))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1caccde25ce920bb1db6699d2dacf584" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(A0) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga48ca995676eb8390d5b72de95b162f1d" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(A0) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3abea1c31d6c20f3654bf122e5c1d620" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(A0) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3096fca21fa31883b22c40eb3e8b99f4" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(A0)&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7a3e10bac5a390147dcdf54a5ada0778" rel="nofollow" target="_blank">event</a> (R(*func)(B0, A0), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga04e574c5c425fa77b2e5d17f5b0186bc" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, A0), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4db2b9c38247f96f2ea3c9e41c130aed" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, A0) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5d499f71e6824f921139e3ebd15a39ec" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, A0) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0c7676d9c44259b67f0175c1da1403dc" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, A0) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad4937cf00d984ceda16a074e75a45816" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, A0)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga648476c832db891ae568ff47a3a71700" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, A0), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga253ab50bdab573d926bf19d6f02f872a" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, A0), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0273c4ce5b0e97ee82e654f6a28d6a36" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, A0) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9a1c8c8ac038219c39755347d5d7f2d6" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, A0) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga019a94d0602bc0c584492cd9a271c0db" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, A0) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf2e6fbcd6b65f25b3325ef95228ed1f8" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, A0)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gafa759baf0292e47dc6824e6defa38707" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, A0), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gada916b0d02d14120c630ad70600b0d4d" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, A0), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7787c1332ee6f50fdf004f1116a7294c" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, A0) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga157d75c88cafb3003945b41b08ef6a76" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, A0) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga357ac1296faa357355db940584abc91d" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, A0) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf5871e2dd1306df417bffa4db9292f81" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, A0)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga63a50915015f22b9fecdead80c80c219" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, A0), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1a82d5391f7f2672e69e60eb736ce2b4" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, A0), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9f640e761ada1441ec76db9086cb0b28" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, A0) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gac286d6b640acb46140e1b992934753e6" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga25b408e0cad1d9b00536ecda7c740fb3" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga499abce7750618455172ca4a72101d3c" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, A0)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1c5b99dc591f26c47b90a950f7444e26" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4, A0), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1bdc0dee470f9c61adcd72ff94816194" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0fb53d69e63d24072ac182d3cab106b5" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga866575ad974dfc7e7c8232c5c88fe621" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gacc0a34cf4d836f1a5657b6f7f6e439b7" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga371736ccec49be534ece214befd0e0f8" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4, A0)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga52a4dcae60b1e7fa1fb31ccdaa818ea7" rel="nofollow" target="_blank">event</a> (R(*func)(A0, A1))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf93a757a0c60d3c309d77b6b5b3781b7" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(A0, A1))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga584c16c6d93cb2ef73389c988b633a26" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(A0, A1) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga928896437377de2a827b95572fa22185" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(A0, A1) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga81a52cc29a7dbd5eb8aed2f00625aa88" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(A0, A1) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4e4e2840550d11df28749e89281ed9cb" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(A0, A1)&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga2d3980c3786c500c2eb3e9202231f131" rel="nofollow" target="_blank">event</a> (R(*func)(B0, A0, A1), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1fbf683a3ef9fece372fcc71b3706fd8" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, A0, A1), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga93ea8b8996fcdf65a183efdbbf5348ce" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, A0, A1) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga6f230eee55d566b321a7a5a325a0c423" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, A0, A1) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0bd861bb18aac365de45157d7c8b672a" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, A0, A1) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga08a03f6395f5211e0ce39a370410c21a" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, A0, A1)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga134cf449de60c1cf555791d627197847" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, A0, A1), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4ed0de5f220500adb12bb1090211d177" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, A0, A1), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaaefe6320c8b4d4184799cf0ca85318da" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, A0, A1) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7fba7e90aeaebdcfa57a1b3fdc22db40" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, A0, A1) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa1311cefa5abdeb20c6b73f7a7f85153" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, A0, A1) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gae52eff8575944574729fac61027a1795" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, A0, A1)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga980ec8c0390a85690f7463a58d2d7fd9" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, A0, A1), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga81713da560442f530adfd15fe203debb" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, A0, A1), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga28a941ec5a1be4c033137e149b4ff3a7" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, A0, A1) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa26dc15d668071e0586e4f43ea706070" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0d9ee7d294a36623a24921dfd1f09c32" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga39e8a9fecafaee17e5e4a4a6e48db637" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, A0, A1)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga13f0cf3568e705194da6333efce366aa" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, A0, A1), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaad8da94e7c3f929583875348388df2b7" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga27232e16744017a7d205d12e56448a18" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga2b7e02bace8a992967950538b58b70f6" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7073f71c1a489fbc87a597dc05e6ef46" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf7ef373f51be17e46dce7676c64ec7de" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, A0, A1)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7bf5f8f4b0b550f42828d27da9a3d6dc" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4, A0, A1), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gadb321f8737048902152e202dd2763c06" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga6302af073ff60e141608182ca9d0c385" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4159f834421e53c8c48fc7c5590809b1" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7eddd461b1ea6de1b81914a6d080caad" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga504e6f1e521a4603ae146c36b619652e" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4, A0, A1)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga2952b9d5c169ea587fe9effc1b7872b6" rel="nofollow" target="_blank">event</a> (R(*func)(A0, A1, A2))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga4c7b59443a22b940064c150b22d23aea" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(A0, A1, A2))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8dc5b730e0bd78451733ff57616605d5" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(A0, A1, A2) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaeefb0a19d25bc508aed50f77c767c087" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(A0, A1, A2) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga182ec9e677bdf5fd642a33e38366f699" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(A0, A1, A2) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga91fa82b7d8e421189851545fb85e021f" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(A0, A1, A2)&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9ac3a2efa54ee36fa9f024854ef2f7d1" rel="nofollow" target="_blank">event</a> (R(*func)(B0, A0, A1, A2), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga56c4d56039577086dc4df9d440fc674d" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, A0, A1, A2), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga02ff133462c13002f07f557c1302b3d5" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, A0, A1, A2) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga068d373417d7f932ff1a6b1675ed977f" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, A0, A1, A2) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8e67d29862396a10e536733350131135" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, A0, A1, A2) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga6b23c131ca4a94a902ce666f92c91da8" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, A0, A1, A2)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga386f35b9fe478823a5df446c873d60a3" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, A0, A1, A2), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gae56c3e026002a47529cddae66020d168" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, A0, A1, A2), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3f2dc99c11a4cb232694d440bd632c95" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, A0, A1, A2) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga52b630bbba0bad86fdac34c6415a5085" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gada4f20680b585f0f471720e015c9d47d" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab8d18d2c42b3138bae2e5ff957da6144" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, A0, A1, A2)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga894946b296675cf6cacdc010fb984a35" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, A0, A1, A2), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab9780464562b85c81173f934b8e370cc" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga54e2ce3d4716d179679ba4b84250cb56" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga21b0064e1d3b2550e6aef29036cb5401" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga599151333bc246453560abfa4a3e4778" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaabad8a421bdc284aae5b6a746daaf3aa" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, A0, A1, A2)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga56b590acf235d3b575e7ff9142b55831" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, A0, A1, A2), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga469d5adc3356995e80429f46eed48574" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gacafb54d7741a56912e027152dec46809" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0182bf37cfe7783c7a07779226435dca" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gabd35fb1f07d799b944b9591a09975ef6" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga99f0528221cb6145b6c267074c9de295" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, A0, A1, A2)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga508e529bc808780a0684b897ca7640d2" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4, A0, A1, A2), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga683f0ed274404a4d82948e6306a77b66" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8c850c6416f92d49b1dc9c86d10ef49a" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab1e46097a3d067e8d8e9a42d91345b11" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaed195b95e4d5ee05cd015735ea09721d" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga74bbc002f46274fd3031a436daa53299" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4, A0, A1, A2)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga113ef2233977f6cbb326d60db5b50e14" rel="nofollow" target="_blank">event</a> (R(*func)(A0, A1, A2, A3))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab80fe42b7d12a2068c1e61bd9e1780c7" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(A0, A1, A2, A3))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1a9777700ee3956ed35a450d3f421a80" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(A0, A1, A2, A3) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga75af7d83766c03791e4113b8b4a25112" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(A0, A1, A2, A3) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga817fa00adaaff13a762b7dd1a0422167" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(A0, A1, A2, A3) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaec180672aff6bea53b80525652ad5e1f" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(A0, A1, A2, A3)&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa3998968215be1216e2f5c5ad749c93c" rel="nofollow" target="_blank">event</a> (R(*func)(B0, A0, A1, A2, A3), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa3026f2258f953973ed57f73102b52dd" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, A0, A1, A2, A3), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gac900c261c67be51340d91487a6f3b94b" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, A0, A1, A2, A3) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf7ae310fdecfed3593dd1f749081e996" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, A0, A1, A2, A3) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9b3424cd4f5542d0e9d6206381c2bd5e" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, A0, A1, A2, A3) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa58d476115734860b1df76e36035c4b9" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, A0, A1, A2, A3)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3a8fc7dc7c48e2caeb2e7f7517d818de" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, A0, A1, A2, A3), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0d1c8b79507b817a7f54fee8cc68cb02" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaafe1670fcfe14c9664e399c2d27dd9e6" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad3ba78bb3694b8d5351b351db7b65db3" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3162ec548cbcf02d16efd35550071d1d" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8bca5e3d5eff9d1a54b94cfd58b4e0a4" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, A0, A1, A2, A3)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga743e343edaea73fb40eceb21b5dd99a5" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa9259486da3cbe52044e838508d5ba5a" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaca941713aaea7657e89cd7ca2274fc62" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8bf230bf4e5cd07a50c8f0f618d38cc7" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8e2bacc9191adf84b96214c991cbb55c" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga61602af96b705cc16225ffd590ced40e" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, A0, A1, A2, A3)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3f2ae4df8d742955627b11bae6b0919a" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa37ec7cff57eebd3c9b44007e934fc21" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gac990c21d4c8bcc0ec7c72977d34ee907" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad82659c95ffe2614ec8758a79ff0c2f4" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga48cfc88a378255f459c39dafbd1f2eb8" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga844ec5f6785188112b5d6d7e08d2be0d" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, A0, A1, A2, A3)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga78adab8091736bfbafb9a1081856e8fe" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaf9944fdfe276031e5a259dce1cbdceb1" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga81f431aa1e651b2c38812824a6ee5a5c" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7c55078e622e876a93029b4bdff00116" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9159515c5fd0ba361cdcfb6939ea3c5d" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gac349ed1654012ceaa47bac68cdb04b7a" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4, A0, A1, A2, A3)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga9375d9a35c4976c7e98555ab87e20b3a" rel="nofollow" target="_blank">event</a> (R(*func)(A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad475768c598f61a883eedc6c51b02758" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga08518d67eed8e86520a53f54e87b1f73" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(A0, A1, A2, A3, A4) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga602f29681f8f0a31ecbcb260db001f3d" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga999869cf25028849a7bfb978ecaf5a36" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga78d96a860b37b2ffd5b51588d4c747cf" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(A0, A1, A2, A3, A4)&gt; cb)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga924feb9dd0b6ad6d434d842ca5aa1dc9" rel="nofollow" target="_blank">event</a> (R(*func)(B0, A0, A1, A2, A3, A4), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga21905383ec40ca2570a1c3d70819b7ca" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, A0, A1, A2, A3, A4), C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga536c84c18958ad7c1d18d36b7fab3216" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, A0, A1, A2, A3, A4) const, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga28a9f402415b5755de8a8d724a4d6b72" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, A0, A1, A2, A3, A4) volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8427e40369d1135982f9b85a2783fdaf" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, A0, A1, A2, A3, A4) const volatile, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename C0 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gacd74121252a6b418a39d91a5e6c1cf10" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, A0, A1, A2, A3, A4)&gt; cb, C0 c0)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0c6c3c3c90346f30ed21f6dca473a02d" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, A0, A1, A2, A3, A4), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gafa1e70a25f6e029357e0aa0a0a358e9d" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3, A4), C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga48c4b357232137e92eff8d27aa5c0cbb" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3, A4) const, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga1033a4d7153244fcceba43ed6c90df11" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3, A4) volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5bfd76f2a032fb2d4efddfbf9744148f" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, A0, A1, A2, A3, A4) const volatile, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename C0 , typename C1 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5ea398d2e814887e8415cd4d6a107cbf" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, A0, A1, A2, A3, A4)&gt; cb, C0 c0, C1 c1)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gab69f772cece45bd317d51e53f5ab5f87" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gada1301d0ee8dac9ad6af263fe8aba08d" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga7ff30a8cc766a72f91c2b7aad107fae6" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3, A4) const, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga0697bd9272552138af0cf54a21ad8f43" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3, A4) volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga95aa7e6a3f6b68137b4dc18144172b50" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, A0, A1, A2, A3, A4) const volatile, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename C0 , typename C1 , typename C2 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gac3222e804fafd449663b79783f447739" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, A0, A1, A2, A3, A4)&gt; cb, C0 c0, C1 c1, C2 c2)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga96b5c8ec895614256a0fcd5093709e0b" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gad72b6084c5b02139c2c5fcea63fbeecf" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaeef43db98936bc82f3fc7cbef4890ea4" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3, A4) const, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaa7c6030a7568fe28c492cc12507ce887" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3, A4) volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5fbd606c3fa175cf636771bd82556261" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, A0, A1, A2, A3, A4) const volatile, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename C0 , typename C1 , typename C2 , typename C3 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga8a69d88c80c237fe91925ac61e4f9989" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, A0, A1, A2, A3, A4)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaaf743191a66a303f0a1f3fc5531db8b8" rel="nofollow" target="_blank">event</a> (R(*func)(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5546ddbc3ad3e22dbaa3bda3062962cf" rel="nofollow" target="_blank">event</a> (T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4), C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga3b2cd7cfde9c93f0e9406a9aed5ec87b" rel="nofollow" target="_blank">event</a> (const T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4) const, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gaebaff84929eb12ebcb9d164b210dd78f" rel="nofollow" target="_blank">event</a> (volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4) volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#gae8f06682fb33568b49e06298d59aacb6" rel="nofollow" target="_blank">event</a> (const volatile T *obj, R(T::*method)(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4) const volatile, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr><tr><td colspan="2">template&lt;typename R , typename B0 , typename B1 , typename B2 , typename B3 , typename B4 , typename C0 , typename C1 , typename C2 , typename C3 , typename C4 , typename A0 , typename A1 , typename A2 , typename A3 , typename A4 &gt;</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classevents_1_1_event.html" rel="nofollow" target="_blank">Event</a>&lt; void(A0, A1, A2, A3, A4)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/group__events.html#ga5aa22caa92e3fb339dfde32343f789e9" rel="nofollow" target="_blank">event</a> (<a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; R(B0, B1, B2, B3, B4, A0, A1, A2, A3, A4)&gt; cb, C0 c0, C1 c1, C2 c2, C3 c3, C4 c4)</td>
		</tr></tbody></table>
        <table><tbody><tr><td colspan="2">静态保护的成员函数</td>
		</tr><tr><td colspan="2"><a id="ad53e21871b832ae6ca1aed16960238a3" target="_blank"></a> template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>function_call</strong> (void *p)</td>
		</tr><tr><td colspan="2"><a id="ac406302ee4546f6a522a52e791f1d275" target="_blank"></a> template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">static void&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>function_dtor</strong> (void *p)</td>
		</tr></tbody></table>
        <table><tbody><tr><td colspan="2">受保护的属性</td>
		</tr><tr><td style="vertical-align:top;"><a id="aaf408e6faff9df9b253be6bfabfe7ff3" target="_blank"></a> struct <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/structequeue.html" rel="nofollow" target="_blank">equeue</a>&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_equeue</strong></td>
		</tr><tr><td style="vertical-align:top;"><a id="a00bc3b8ea556ca4685b4e3c685c3cdc8" target="_blank"></a> <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">mbed::Callback</a>&lt; void(int)&gt;&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>_update</strong></td>
		</tr></tbody></table>
        <table><tbody><tr><td colspan="2"><a name="friends" target="_blank"></a> 友元</td>
		</tr><tr><td colspan="2"><a id="a220e3dbca6fc464081a98147b97f633c" target="_blank"></a> template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">class&nbsp;</td>
			<td style="vertical-align:bottom;"><strong>Event</strong></td>
		</tr></tbody></table>
        
## 共享事件队列参考
[mbed_shared_queues.h](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/mbed__shared__queues_8h_source.html)

## EventQueue 示例: 推迟中断上下文
代码在两个不同的上下文中执行两个处理函数（rise_handler 和 fall_handler）：

1. 在中断上下文中，当在 SW2（rise_handler）上检测到上升沿时。
2. 在 SW2（fall_handler）上检测到下降沿时，在事件循环的线程函数的上下文中。您可以使用 fall_handler 函数作为 queue.event() 的参数来指定 fall_handler 在用户上下文中运行而不是在中断上下文中运行。
[main.cpp](https://os.mbed.com/teams/mbed_example/code/events_ex_1/file/6ae734681f16/main.cpp)       
```
#include "mbed.h"
#include "mbed_events.h"
 
DigitalOut led1(LED1);
InterruptIn sw(SW2);
EventQueue queue(32 * EVENTS_EVENT_SIZE);
Thread t;
 
void rise_handler(void) {
    // Toggle LED
    led1 = !led1;
}
 
void fall_handler(void) {
    printf("fall_handler in context %p\r\n", Thread::gettid());
    // Toggle LED
    led1 = !led1;
}
 
int main() {
    // Start the event queue
    t.start(callback(&queue, &EventQueue::dispatch_forever));
    printf("Starting in context %p\r\n", Thread::gettid());
    // The 'rise' handler will execute in IRQ context
    sw.rise(rise_handler);
    // The 'fall' handler will execute in the context of thread 't'
    sw.fall(queue.event(fall_handler));
}
``` 
 
## 共享事件示例：推迟中断上下文
与前面的示例一样，这会从中断延迟到事件队列线程。但是，它不是创建自己的线程，而是使用共享事件队列 - 可能与其他系统组件共享并保存 RAM。

在共享事件队列时，您应该限制事件函数的执行时间，以避免过度延迟其他用户的事件。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/Shared_Events_1/file/7c7d5b625e59/main.cpp)   
```
#include "mbed.h"
#include "mbed_events.h"
 
DigitalOut led1(LED1);
InterruptIn sw(SW2);
 
void rise_handler(void) {
    // Toggle LED
    led1 = !led1;
}
 
void fall_handler(void) {
    printf("fall_handler in context %p\r\n", Thread::gettid());
    // Toggle LED
    led1 = !led1;
}
 
int main() {
    // Request the shared queue
    EventQueue *queue = mbed_event_queue();
    printf("Starting in context %p\r\n", Thread::gettid());
    // The 'rise' handler will execute in IRQ context
    sw.rise(rise_handler);
    // The 'fall' handler will execute in the context of the shared queue thread
    sw.fall(queue->event(fall_handler));
}
``` 
## EventQueue 示例: 将事件发布到队列中
下面的代码演示了在延迟之后调用的排队函数以及定期调用的排队函数。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/events_ex_2/file/488fe91e2e80/main.cpp)       
```
#include "mbed_events.h"
#include <stdio.h>
 
int main() {
    // creates a queue with the default size
    EventQueue queue;
 
    // events are simple callbacks
    queue.call(printf, "called immediately\n");
    queue.call_in(2000, printf, "called in 2 seconds\n");
    queue.call_every(1000, printf, "called every 1 seconds\n");
 
    // events are executed by the dispatch method
    queue.dispatch();
}
```
## EventQueue 示例: 链接来自多个队列的事件
事件队列很容易与模块边界对齐，事件调度可以隐式地同步内部状态。多个模块可以使用独立的事件队列，但仍然可以通过EventQueue :: chain 函数组成。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/events_ex_3/file/fca134a32b61/main.cpp)       
```
#include "mbed_events.h"
#include <stdio.h>
 
/**
Event queues easily align with module boundaries, where internal state can be 
implicitly synchronized through event dispatch. Multiple modules can use 
independent event queues, but still be composed through the EventQueue::chain function.
**/
 
int main() {
    // Create some event queues with pending events
    EventQueue a;
    a.call(printf, "hello from a!\n");
    
    EventQueue b;
    b.call(printf, "hello from b!\n");
    
    EventQueue c;
    c.call(printf, "hello from c!\n");
    
    // Chain c and b onto a's event queue. Both c and b will be dispatched
    // in the context of a's dispatch function.
    c.chain(&a);
    b.chain(&a);
    
    // Dispatching a will in turn dispatch b and c, printing hello from
    // all three queues
    a.dispatch();
}
```
## 共享事件示例：从 main 运行共享队列
为了进一步节省 RAM，如果初始化后在 main 函数中没有其他工作要做，则可以从那里调度全局事件队列，从而无需创建单独的调度线程。

为此，请将 mbed_app.json 配置选项 events.shared-dispatch-from-application 设置为 true，并向 main 添加调度调用，如本例所示。（打印现在显示启动和 fall_handler 的相同上下文）。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/Shared_Events_2/file/154179bdc39d/main.cpp)   
```
#include "mbed.h"
#include "mbed_events.h"
 
DigitalOut led1(LED1);
InterruptIn sw(SW2);
 
void rise_handler(void) {
    // Toggle LED
    led1 = !led1;
}
 
void fall_handler(void) {
    printf("fall_handler in context %p\r\n", Thread::gettid());
    // Toggle LED
    led1 = !led1;
}
 
int main() {
    // Request the shared queue
    EventQueue *queue = mbed_event_queue();
    printf("Starting in context %p\r\n", Thread::gettid());
    // The 'rise' handler will execute in IRQ context
    sw.rise(rise_handler);
    // The 'fall' handler will execute in the context of the shared queue (actually the main thread)
    sw.fall(queue->event(fall_handler));
    // Setup complete, so we now dispatch the shared queue from main
    queue->dispatch_forever();
}
``` 