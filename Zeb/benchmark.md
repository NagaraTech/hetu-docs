## Benchmark

```shell
❯ go test -bench='^\QBenchmarkStartCluster\E$'

port: 33333, wsport: 23333, id: 406b4c9bb2117df0505a58c6c44a99c8817b7639d9c877bdbea5a8e4e0412740
port: 33334, wsport: 23334, id: f78e5a39e3d433986c4b8026d0baeb62b7eb845c29bb83a04b79d645ef7efbba
port: 33335, wsport: 23335, id: 3724b4e85737f7a77b18737535cecd676db38e88514bf0387c2d8fa62905f8eb
port: 33336, wsport: 23336, id: adcfaf62c9a25c7cb3b7fff13f0d0a3b8ef1d120fd06d25873a406a347485ce3
port: 33337, wsport: 23337, id: e8fe8612ea7f1efc861b8433caa8f8f2b193ec92459d99c4dad459d5dced0ccd
port: 33338, wsport: 23338, id: 77d04b8cef779465f06bfbc74095eea904ae3c8e307b7749850e2b71ffbbbed3
port: 33339, wsport: 23339, id: fc450038489c805d7d6dd418b1bb459ec549bf36fa89923f2250e78576440aa2
port: 33340, wsport: 23340, id: 76c0047f144a94f24115f48be88ef5ba1d45384d167ab42427f64c19a30a0dcb
port: 33341, wsport: 23341, id: ef3ea1a430356331a8e81c3d992f178b87863f9cb7195c0f1cd34418479ba9c3
port: 33342, wsport: 23342, id: 6a4c37d8ea309ea35fa29c66b36942dfd4a35da746477e39da0d997fd3646cd2
```

```shell
   20512	    106857 ns/op
--- BENCH: BenchmarkStartCluster-10
    cluster_test.go:53: 0
    cluster_test.go:40: received: 0
    cluster_test.go:53: 0
    cluster_test.go:40: received: 0
    cluster_test.go:53: 0
    cluster_test.go:40: received: 0
    cluster_test.go:53: 0
    cluster_test.go:40: received: 0
    cluster_test.go:53: 10000
    cluster_test.go:40: received: 10000
	... [output truncated]
PASS
ok  	github.com/bufrr/znet/examples	7.172s
```