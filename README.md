# silk
Silk v3 Encoder / Decoder implement in Golang.

Go 语言版本的 Silk v3 编码/解码器。

可用于解码国内通信软件语音文件。

## Install 获取
```
go get -u github.com/pinwang5776/silk
```

## API 接口
```
func Decode(src io.Reader, opts ...internal.DecodeOpt) ([]byte, error)
func Encode(src io.Reader, opts ...internal.EncodeOpt) ([]byte, error)

// Decode Options 解码选项

// WithSampleRate set decode option, sample rate, default 24000
// 设置 sample rate 参数，默认值 24000
func WithSampleRate(sampleRate int) internal.DecodeOpt {
	return func(dc *internal.DecodeCfg) { dc.SampleRate = sampleRate }
}
```
see [API doc](https://pkg.go.dev/github.com/pinwang5776/silk)

## See also 致谢
- https://github.com/gaozehua/SILKCodec    源码
- https://github.com/kn007/silk-v3-decoder 兼容国内软件的版本
- https://github.com/wdvxdr1123/go-silk    ccgo 转写为 go 的版本
- https://github.com/zxfishhack/go-silk    可直接转 wav 的版本
- [Go语言高级编程 - 第 2 章 CGO 编程](https://chai2010.cn/advanced-go-programming-book/ch2-cgo/index.html)
- https://github.com/sunicy/go-lame 将 pcm 转换为 mp3，适配 go mod 的 fork 版本：https://github.com/youthlin/go-lame

## LICENSE
MIT.

C 源码开源协议见每个文件头部注释。
