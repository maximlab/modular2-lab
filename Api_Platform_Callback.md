## Callback

回调是用户提供的功能，用户可以将其传递给 API。回调允许 API 在其自己的上下文中执行用户代码。

这是回调的技术参考。您应首先阅读 “平台概述” 的 “回调” 部分，以深入了解其用途。

## Callback 类参考

[mbed::Callback< R(A0, A1, A2, A3, A4)> 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html)

<table><tbody><tr><td colspan="2">公共成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a20825b02c441e6fbf9b8c0da18c63c3b" rel="nofollow" target="_blank">Callback</a> (R(*func)(A0, A1, A2, A3, A4)=0)</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a63593f9ee9740ba29b8bb32a9f007f06" rel="nofollow" target="_blank">Callback</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; R(A0, A1, A2, A3, A4)&gt; &amp;func)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ae016caa48f77914c69cd880730182c58" rel="nofollow" target="_blank">Callback</a> (U *obj, R(T::*method)(A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#aa3d95d821c020357e310d2605592269f" rel="nofollow" target="_blank">Callback</a> (const U *obj, R(T::*method)(A0, A1, A2, A3, A4) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a9534573cf0c4a7842345e29887005155" rel="nofollow" target="_blank">Callback</a> (volatile U *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#aa73af2947c97682fc16fc0eb1210c3ba" rel="nofollow" target="_blank">Callback</a> (const volatile U *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a4cd63df22ffa1ff680e5742ba9004e2d" rel="nofollow" target="_blank">Callback</a> (R(*func)(T *, A0, A1, A2, A3, A4), U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a13dd878d1091bfe82ba95453095c2f0c" rel="nofollow" target="_blank">Callback</a> (R(*func)(const T *, A0, A1, A2, A3, A4), const U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a7afbf0a4df52cdf67ba4c5e193277008" rel="nofollow" target="_blank">Callback</a> (R(*func)(volatile T *, A0, A1, A2, A3, A4), volatile U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#abd26c568b29fdc1090ea2a384ba4eb32" rel="nofollow" target="_blank">Callback</a> (R(*func)(const volatile T *, A0, A1, A2, A3, A4), const volatile U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ad5a1a4b64c186ec54dba4f68a5a56ce9" rel="nofollow" target="_blank">Callback</a> (F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#adc3064027ce69883eec9376af0ecc9bc" rel="nofollow" target="_blank">Callback</a> (const F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a71a3a9d0ad00991cdaa261b39dc880cf" rel="nofollow" target="_blank">Callback</a> (volatile F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a628b230deeb133b893f426a9dd391738" rel="nofollow" target="_blank">Callback</a> (const volatile F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ab1445febb4101b28f0488be2ab77b734" rel="nofollow" target="_blank">Callback</a> (U *obj, R(*func)(T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a8c3a2b42568d5be06f214717251e9bce" rel="nofollow" target="_blank">Callback</a> (const U *obj, R(*func)(const T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a2a937dccb768646f8878e4d1c09abd75" rel="nofollow" target="_blank">Callback</a> (volatile U *obj, R(*func)(volatile T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a378a92fec6fe78e7656118748d0e00ee" rel="nofollow" target="_blank">Callback</a> (const volatile U *obj, R(*func)(const volatile T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#aa628baf42353cd60400252a7a5d3acde" rel="nofollow" target="_blank">~Callback</a> ()</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a905e914bb0d8f98948c3cc670f288536" rel="nofollow" target="_blank">attach</a> (R(*func)(A0, A1, A2, A3, A4))</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ad8b8615214b0e06d1f4806434e689a5e" rel="nofollow" target="_blank">attach</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a>&lt; R(A0, A1, A2, A3, A4)&gt; &amp;func)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#af411acad8f46e1fdeaa6c72c64f21e39" rel="nofollow" target="_blank">attach</a> (U *obj, R(T::*method)(A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a8f19afc976cbefdfa087449670fdecd2" rel="nofollow" target="_blank">attach</a> (const U *obj, R(T::*method)(A0, A1, A2, A3, A4) const)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a68cb103db1f567f343609b6cc59d6880" rel="nofollow" target="_blank">attach</a> (volatile U *obj, R(T::*method)(A0, A1, A2, A3, A4) volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a7091296f312f20c7f22a7af6d8d989b6" rel="nofollow" target="_blank">attach</a> (const volatile U *obj, R(T::*method)(A0, A1, A2, A3, A4) const volatile)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#acbb147d2bf5978a86a61ebeb51675d60" rel="nofollow" target="_blank">attach</a> (R(*func)(T *, A0, A1, A2, A3, A4), U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a08d7145bd6021268c4fb5c2edcca1354" rel="nofollow" target="_blank">attach</a> (R(*func)(const T *, A0, A1, A2, A3, A4), const U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#aaa03b46559d7ada0a944aedd88bd4ad5" rel="nofollow" target="_blank">attach</a> (R(*func)(volatile T *, A0, A1, A2, A3, A4), volatile U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a5951f1aabd0ff74512f0aee11146e34c" rel="nofollow" target="_blank">attach</a> (R(*func)(const volatile T *, A0, A1, A2, A3, A4), const volatile U *arg)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a27990ba06af19335893d3d17d8b8d6b4" rel="nofollow" target="_blank">attach</a> (F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a3f48d100803e1e8d15e7c5de34645c9a" rel="nofollow" target="_blank">attach</a> (const F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a5ac98efe726f00fc58d735b3058140f6" rel="nofollow" target="_blank">attach</a> (volatile F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename F &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a47c9e14c1faafc8d607cda78dd5dd4ef" rel="nofollow" target="_blank">attach</a> (const volatile F f,)</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ad8fd4a4a837d2daed91a929b2eaa99d4" rel="nofollow" target="_blank">attach</a> (U *obj, R(*func)(T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#adb1d9c372c34e20c661b53fb294a4576" rel="nofollow" target="_blank">attach</a> (const U *obj, R(*func)(const T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a25269216afcf783898f14e8e22112fca" rel="nofollow" target="_blank">attach</a> (volatile U *obj, R(*func)(volatile T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td colspan="2">template&lt;typename T , typename U &gt;</td>
		</tr><tr><td style="vertical-align:top;">void&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a146d066174e02b88cc808031241ee801" rel="nofollow" target="_blank">attach</a> (const volatile U *obj, R(*func)(const volatile T *, A0, A1, A2, A3, A4))</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#ab8ce4dda05f084ab3946dc88b39d76cb" rel="nofollow" target="_blank">operator=</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback.html" rel="nofollow" target="_blank">Callback</a> &amp;that)</td>
		</tr><tr><td style="vertical-align:top;">R&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a3dfb2779b6ad16a74bcbd3753a7f864d" rel="nofollow" target="_blank">call</a> (A0 a0, A1 a1, A2 a2, A3 a3, A4 a4) const</td>
		</tr><tr><td style="vertical-align:top;">R&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a63aa30d028139787f1471af50658824e" rel="nofollow" target="_blank">operator()</a> (A0 a0, A1 a1, A2 a2, A3 a3, A4 a4) const</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_callback_3_01_r_07_a0_00_01_a1_00_01_a2_00_01_a3_00_01_a4_08_4.html#a8624f133e1e5c8b3acceaed20e001fcf" rel="nofollow" target="_blank">operator bool</a> () const</td>
		</tr></tbody>
    </table>

## 带回调的串行直通示例

[main.cpp](https://os.mbed.com/users/mbedAustin/code/SerialPassthrough/file/96cb82af9996/main.cpp)    
```
#include "mbed.h"
 
RawSerial  pc(USBTX, USBRX);
RawSerial  dev(D1, D0);
DigitalOut led1(LED1);
DigitalOut led4(LED4);
 
void dev_recv()
{
    led1 = !led1;
    while(dev.readable()) {
        pc.putc(dev.getc());
    }
}
 
void pc_recv()
{
    led4 = !led4;
    while(pc.readable()) {
        dev.putc(pc.getc());
    }
}
 
int main()
{
    pc.baud(9600);
    dev.baud(9600);
 
    pc.attach(&pc_recv, Serial::RxIrq);
    dev.attach(&dev_recv, Serial::RxIrq);
 
    while(1) {
        sleep();
    }
}
```
## 带回调的线程示例

Callback API 提供了一种将参数传递给生成线程的便捷方法。此示例在 Callback 中使用 C 函数指针。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/rtos_threading_with_callback/file/d4b2a035ffe3/main.cpp) 
```
#include "mbed.h"
 
Thread thread;
DigitalOut led1(LED1);
volatile bool running = true;
 
// Blink function toggles the led in a long running loop
void blink(DigitalOut *led) {
    while (running) {
        *led = !*led;
        wait(1);
    }
}
 
// Spawns a thread to run blink for 5 seconds
int main() {
    thread.start(callback(blink, &led1));
    wait(5);
    running = false;
    thread.join();
}
```
## 声纳的例子

下面是一个示例，它以最小的 Sonar 类的形式使用回调文档简介中讨论的所有内容。此示例在 Callback 中使用 C++ 类和方法。

[main.cpp](https://os.mbed.com/teams/mbed_example/code/callback-sonar-example/file/1713cdc51510/main.cpp)       
```
#include "mbed.h"
 
/**
 *  Sonar class for the HC-SR04
 */
class Sonar {
    DigitalOut   trigger;
    InterruptIn  echo;     // calls a callback when a pin changes
    Timer        timer;
    Timeout      timeout;  // calls a callback once when a timeout expires
    Ticker       ticker;   // calls a callback repeatedly with a timeout
    int32_t      begin;
    int32_t      end;
    float        distance;
 
public:
    /**
     *  Sonar constructor
     *  Creates a sonar object on a set of provided pins
     *  @param trigger_pin  Pin used to trigger reads from the sonar device
     *  @param echo_pin     Pin used to receive the sonar's distance measurement
     */
    Sonar(PinName trigger_pin, PinName echo_pin) : trigger(trigger_pin), echo(echo_pin) {
        trigger = 0;
        distance = -1;
 
        echo.rise(callback(this, &Sonar::echo_in));    // Attach handler to the rising interruptIn edge
        echo.fall(callback(this, &Sonar::echo_fall));  // Attach handler to the falling interruptIn edge
    }
 
    /**
     *  Start the background task to trigger sonar reads every 100ms
     */
    void start(void) {
        ticker.attach(callback(this, &Sonar::background_read), 0.01f);
    }
 
    /**
     *  Stop the background task that triggers sonar reads
     */
    void stop(void) {
        ticker.detach();
    }
 
    /**
     *  Interrupt pin rising edge interrupt handler. Reset and start timer
     */
    void echo_in(void) {
        timer.reset();
        timer.start();
        begin = timer.read_us();
    }
 
    /**
     *  Interrupt pin falling edge interrupt handler. Read and disengage timer.
     *  Calculate raw echo pulse length
     */
    void echo_fall(void) {
        end = timer.read_us();
        timer.stop();
        distance = end - begin;
    }
 
    /**
     *  Wrapper function to set the trigger pin low. Callbacks cannot take in both object and argument pointers.
     *  See use of this function in background_read().
     */
    void trigger_toggle(void) {
        trigger = 0;
    }
 
    /**
     *  Background callback task attached to the periodic ticker that kicks off sonar reads
     */
    void background_read(void) {
        trigger = 1;
        timeout.attach(callback(this, &Sonar::trigger_toggle), 10.0e-6);
    }
 
    /**
     *  Public read function that returns the scaled distance result in cm
     */
    float read(void) {
        return distance / 58.0f;
    }
};
 
 
int main() {
    // Create sonar object on pins D5 and D6
    Sonar sonar(D5, D6);
    // Begin background thread sonar acquires
    sonar.start();
 
    while(1) {
        wait(0.1f);
        // Periodically print results from sonar object
        printf("%f\r\n", sonar.read());
    }
}
```
## 调用回调

回调会使函数调用运算符重载，因此您可以像正常函数一样调用 Callback：
```
void run_timer_event(Callback<void(float)> on_timer) {
    on_timer(1.0f);
}
```
唯一需要注意的是 Callback 类型具有空回调，就像空函数指针一样。未初始化的回调为 null，如果调用它们则断言。如果您希望呼叫始终成功，则需要先检查它是否为空。
```
void run_timer_event(Callback<void(float)> on_timer) {
    if (on_timer) {
        on_timer(1.0f);
    }
}
```
Callback 类在 C++ 中称为 “具体类型”。也就是说，Callback 类足够轻量级，可以像 int，pointer 或其他基本类型一样传递。