`AddAddress` modifies the memory address(es) of the following condition by the calculated value. It works similar to [`AddSource`](AddSource-Flag), but modifies the address, not the resulting value. Additionally, it affects addresses on both sides of the condition.

`AddAddress` only affects the next condition. If multiple `AddAddress` lines are chained together, each lookup in the chain will be altered; the values won't all be added to the final lookup.

![image](https://user-images.githubusercontent.com/32680403/68913137-9396d780-0717-11ea-871f-150903408d5f.png)

The 32-bit value at 0x0112F8 is a pointer to the data for the first character in the party. When the party order changes, the pointer will point at a different block of memory, but data within the block will have the same structure.

* The value is an address in the actual system representation and differs from the addresses provided by the memory inspector. However, you can rely on the fact that the memory inspector represents the same memory, so while the actual address may differ, the sequence of bytes does not.

To translate the real pointer to a memory inspector address, we compare the two values. For example:

- The 32-bit value at 0x0112F8 is 0x800110B8.
- The memory we're interested in is at 0x011114 in the memory inspector.
- Using a 24-bit read instead of a 32-bit read gives us 0x0110B8
- 0x011114 - 0x0110B8 = 0x00005C, so that becomes the "base address" in the second condition.

## Types of Pointers

`AddAddress` is how RAIntegration handles pointers. There are four major types of pointer support:

**Direct Pointer**: The pointer contains another address that is referenced without modification. These are most commonly used for string pointers. To use a direct pointer, the base address to which the pointer is added would be 0.

**Indirect Pointer**: The pointer contains another address that indicates the start of some block of data. The data of interest is a fixed number of bytes into the block of data. These are commonly used for attributes of a character/object.

For both Direct and Indirect Pointers, the `AddAddress` line should reference the pointer, and the address in the following line should be the offset into the block of data for the information relevant to the condition. While you would typically use 0 for a Direct Pointers, the following line would also contain any value necessary to convert between a real address and a memory inspector address.

The example above is an Indirect Pointer, where the data is 0x5C bytes into a block of data. The conversion from a real address to a memory inspector address is handled by using a 24-bit read instead of a 32-bit read.

**Array Index**: The pointer contains an offset to apply to a fixed pointer.

**Scaled Array Index**: The pointer contains an offset to apply to a fixed pointer after it has been scaled.

For Array Indices, the `AddAddress` line should reference the offset to apply, and the following line should contain the address of the first element of the array (index 0). For example:

```
AddAddress 16-bit Mem 0x1234
           8-bit  Mem 0x4567
```
Would read a 16-bit number from 0x1234 and read the single byte that is that many bytes after 0x4567.

To scale an array index, click on the space in the Cmp column for the array index address and select the `*` symbol. Then enter the size of each array item in the second mem/val column. For example:

```
AddAddress 16-bit Mem 0x1234 * Value 4
           8-bit  Mem 0x4567
```
Would read a 16-bit number from 0x1234, multiply it by 4, and read the single byte that is that many bytes after 0x4567.

## Chaining Pointers

`AddAddress` can be chained to perform multi-step lookups, but only one step at a time. As such, you can reference data pointed at by a pointer that's pointed at by another pointer, but you can't reference data in an array that's pointed at by another pointer unless either the array or the array index is at a fixed address.


## Video Tutorial

The experienced achievement creator [wilhitewarrior](https://retroachievements.org/User/wilhitewarrior) made a nice video showing how to work with pointers and AddAddress flag.

You can check it here: <https://www.youtube.com/watch?v=_gk0vYYlm-E>.