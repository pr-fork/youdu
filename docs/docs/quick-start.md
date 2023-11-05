# Quick Start

## Installation

```bash
go get github.com/addcnos/youdu/v2
```

## Usage

```go

package main

import (
	"context"
	"fmt"

	"github.com/addcnos/youdu/v2"
)

func main() {
	client := youdu.NewClient(&youdu.Config{
		Addr:   "http://examaple",
		Buin:   111222333,
		AppId:  "111222333",
		AesKey: "111333445",
	})

	resp, err := client.SendTextMessage(context.Background(), youdu.TextMessageRequest{
		ToUser:  "11111",
		MsgType: youdu.MsgTypeText,
		Text: youdu.MessageText{
			Content: "hello",
		},
	})
	if err != nil {
		panic(err)
	}

	fmt.Println(resp)
}
```