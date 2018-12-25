## NonCopyable

NonCopyable 类可防止类的对象支持复制操作。您可以从其类声明中轻松识别它。如果复制对象，则会产生编译时错误。继承此类会导致私有副本构造和副本分配操作的自动生成，这些操作在派生类中无法访问。

每当类拥有不应复制到另一个类的资源（锁/硬件/文件）时，我们建议使用 NonCopyable 类。

## NonCopyable 类参考

[mbed::NonCopyable< T > 类模板参考](http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html)

<table><tbody><tr><td colspan="2">受保护的成员函数</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html#adec104acab2885bb31b85dd2d95d7b36" rel="nofollow" target="_blank">NonCopyable</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html#a013149ff450465e164381d213899fce9" rel="nofollow" target="_blank">~NonCopyable</a> ()</td>
		</tr><tr><td style="vertical-align:top;">&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html#a7cd186e55733957643dd340ef2a9a2ee" rel="nofollow" target="_blank">NonCopyable</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html" rel="nofollow" target="_blank">NonCopyable</a> &amp;)</td>
		</tr><tr><td style="vertical-align:top;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html" rel="nofollow" target="_blank">NonCopyable</a> &amp;&nbsp;</td>
			<td style="vertical-align:bottom;"><a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html#adbee6f08583cabee6a882ce5283f6625" rel="nofollow" target="_blank">operator=</a> (const <a href="http://os.mbed.com/docs/v5.9/mbed-os-api-doxy/classmbed_1_1_non_copyable.html" rel="nofollow" target="_blank">NonCopyable</a> &amp;)</td>
		</tr></tbody></table>

## NonCopyable 示例

不应发生用于锁定，网络封装，硬件总线等的类的复制对象。Mbed OS 具有不可复制的类，例如Mutex，EventFlags，BusOut，InterruptIn 和 I2C。

## 相关内容

[Mutex API 参考](https://os.mbed.com/docs/v5.9/reference/mutex.html)。

[EventFlags API 参考](https://os.mbed.com/docs/v5.9/reference/eventflags.html)。

[BusOut API 参考](https://os.mbed.com/docs/v5.9/reference/busout.html)。

[InterruptIn API 参考](https://os.mbed.com/interruptin.html)。

[I2C API 参考](https://os.mbed.com/docs/v5.9/reference/i2c.html)。