# grpc-multi-interceptor

grpc-multi-interceptor is a simple library which provides a function to chain multiple `UnaryServerInterceptor`s or `StreamServerInterceptor`s for gRPC.

## Usage

```
import (
	mint "github.com/kazegusuri/grpc-multi-interceptor"
)

func main() {
	uIntOpt := grpc.UnaryInterceptor(mint.NewMultiUnaryServerInterceptor(
		fooUnaryInterceptor,
		barUnaryInterceptor,
	))
	sIntOpt := grpc.StreamInterceptor(mint.NewMultiStreamServerInterceptor(
		fooStreamInterceptor,
		barStreamInterceptor,
	))
	grpc.NewServer(uIntOpt, sIntOpt)
}
```

## Copyright

<table>
  <tr>
    <td>Author</td><td>Masahiro Sano <sabottenda@gmail.com></td>
  </tr>
  <tr>
    <td>Copyright</td><td>Copyright (c) 2016- Masahiro Sano</td>
  </tr>
  <tr>
    <td>License</td><td>MIT License</td>
  </tr>
</table>
