
# int型


# float型
```MSIL

{
  .method private hidebysig static float32 
          fadd(float32 f0,float32 f1) cil managed
  {
    // Code size       9 (0x9)
    .maxstack  2
    .locals init (float32 V_0)
    IL_0000:  nop
    IL_0001:  ldarg.0
    IL_0002:  ldarg.1
    IL_0003:  add
    IL_0004:  stloc.0
    IL_0005:  br.s       IL_0007

    IL_0007:  ldloc.0
    IL_0008:  ret
  } // end of method Program::fadd

  .method private hidebysig static void  Main() cil managed
  {
    .entrypoint
    // Code size       18 (0x12)
    .maxstack  2
    .locals init (float32 V_0)
    IL_0000:  nop
    IL_0001:  ldc.r4     0.1
    IL_0006:  ldc.r4     0.2
    IL_000b:  call       float32 CSHARP.Program::fadd(float32,float32)
    IL_0010:  stloc.0
    IL_0011:  ret
  } // end of method Program::Main
```
# 大于6个参数
    ```S
    ldi $9, 0($16) // save pCallDescrData in s0
    ldw $1, CallDescrData__numStackSlots($9)
    beq $1, LOCAL_LABEL(donestack)
    ldl $5, CallDescrData__pSrc($9)
    s8addl $1, $5, $5  // pSrcEnd=pSrc+8*numStackSlots
    and $1, 1, $28
    beq $28, LOCAL_LABEL(stackloop)
    LOCAL_LABEL(stackloop):
    ldi $sp, -8($sp)
    ldi $5,  -8($5)
    ldl $28, 0($5)
    stl $28, 0($sp)
    ldi $1, -1($1)
    bne $1, LOCAL_LABEL(stackloop)
    ```


# 结构体
来自 <https://learn.microsoft.com/zh-cn/dotnet/api/system.reflection.emit.opcodes.ldloca_s?view=net-6.0> 


| 左对齐| 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 12 | < unsigned int8 >	ldloca.s index | 将局部变量 index 的地址加载到计算堆栈上，格式短。 |


# ref


# out

