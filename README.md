# cdk-go

Go FFI bindings for [cashubtc/cdk](https://github.com/cashubtc/cdk) (Cashu Development Kit), generated via [uniffi-bindgen-go](https://github.com/NordSecurity/uniffi-bindgen-go).

Prebuilt native libraries are included — downstream consumers only need Go.

## Install

```bash
go get github.com/{{CDK_GO_REPO}}
```

## Usage

```go
package main

import (
	"fmt"

	cdk "github.com/{{CDK_GO_REPO}}/bindings/cdkffi"
)

func main() {
	// Create a new wallet
	seed := cdk.GenerateMnemonic()
	fmt.Println("Mnemonic:", seed)
}
```

> **Note:** Requires `CGO_ENABLED=1` (the default on most systems).

## Supported platforms

| OS      | Arch  | Library            |
|---------|-------|--------------------|
| Linux   | amd64 | `libcdk_ffi.so`    |
| Linux   | arm64 | `libcdk_ffi.so`    |
| macOS   | arm64 | `libcdk_ffi.dylib` |
| macOS   | amd64 | `libcdk_ffi.dylib` |
| Windows | amd64 | `cdk_ffi.dll`      |

CGO link flags are automatically selected per platform via build tags. No manual setup required.

## Prerequisites

- Go 1.22+
- `CGO_ENABLED=1`
