**Note**: most likely this technique is not needed for simple games. So, it's not mandatory for jr-devs.

The `AddSource` can be chosen in the Flag column of the Achievement Editor

When a condition has the `Add Source` flag, the value on that memory address is added to the value of the address on the condition right below, and the comparison is made on the condition below the one with the `Add Source` flag. It may sound a bit confusing, but the example below will clarify how this works:

![Add Source Example](https://user-images.githubusercontent.com/8508804/42702176-169aaf44-869f-11e8-979c-487a040e0145.png)

In this example the value in `0x8010` will be added to the value in `0x8020` and the comparison is if this sum is greater than zero.

If the value in `0x8010` is `1` and the value in `0x8020` is `2`, the comparison will be `1 + 2 > 0`, or `3 > 0`.

**Note**:  All the comparison fields on the condition with the `Add Source` flag are ignored.

Trying to summarize the explanation in an image:

![Add Source Explained](https://user-images.githubusercontent.com/8508804/42702180-1712bca0-869f-11e8-9949-11021fa891bb.png)

**Note**: you can use the `Add Source` flag to sum more addresses, like in the example below:

![addsource1](https://user-images.githubusercontent.com/8508804/42702178-16c6d97a-869f-11e8-9c0d-84ef42ec4867.png)
