# CVE-2024-48294: NULL Pointer Dereference in Wondershare PDF Reader

## Description
A NULL pointer dereference vulnerability in `libPdfCore.dll` of Wondershare PDF Reader v1.0.9.2544 allows attackers to cause a Denial of Service (DoS) via a crafted PDF file.

## Vulnerability Type
CWE-476: NULL Pointer Dereference

## Vendor
Wondershare

## Affected Product
- Wondershare PDF Reader - Version 1.0.9.2544

## Affected Component
`libPdfCore.dll`

## Attack Type
Local

## Impact
Denial of Service (DoS)

## Attack Vector
Exploitation requires the user to open a malformed PDF file, which causes a NULL pointer dereference and crashes the application.

## Crash
```
(47e0.271c): Access violation - code c0000005 (first chance)
First chance exceptions are reported before any exception handling.
This exception may be expected and handled.
libPdfCore_7ff9727c0000!CreateFactory+0xc60e52:
00007ff973483322 48897320        mov     qword ptr [rbx+20h],rsi ds:0000000000000020=????????????????
0:029> r
rax=0000000000000008 rbx=0000000000000000 rcx=00000000247eade0
rdx=00000000247f3170 rsi=0000000000000000 rdi=00000000247eade0
rip=00007ff9638d3322 rsp=000000002464e1a0 rbp=00007ff96460b0e0
r8=00000000247eade0  r9=0000000000000001 r10=0000000000000003
r11=000000002464e0c0 r12=0000000024772810 r13=00000000246ea3c0
r14=0000000000000000 r15=0000000000000000
iopl=0         nv up ei pl nz na pe nc
cs=0033  ss=002b  ds=002b  es=002b  fs=0053  gs=002b             efl=00010202
libPdfCore!CreateFactory+0xc60e52:
00007ff9638d3322 48897320        mov     qword ptr [rbx+20h],rsi ds:0000000000000020=????????????????
```

# Stack Exhaustion Due to Uncontrolled Recursion in Wondershare PDF Reader

## Description
An issue was discovered in Wondershare PDF Reader v1.0.9.2544 where endless recursion causes stack exhaustion in `libPdfCore.dll`. If this application is set as the default for opening PDFs, a malformed PDF can repeatedly crash `explorer.exe`.

## Vulnerability Type
CWE-674: Uncontrolled Recursion

## Vendor
Wondershare

## Affected Product
- Wondershare PDF Reader - Version 1.0.9.2544

## Affected Component
`libPdfCore.dll`

## Attack Type
Local

## Impact
Denial of Service (DoS)

## Attack Vector
Exploitation requires setting Wondershare PDF Reader as the default PDF application and opening a malformed PDF file, leading to continuous stack overflow and crashing of `explorer.exe`.

## Crash
```
(2dec.2fc4): Stack overflow - code c00000fd (first chance)
First chance exceptions are reported before any exception handling.
This exception may be expected and handled.
ntdll!RtlpHeapFindListLookupEntry+0x52:
00007ffa0cc6ec7a 8945d8          mov     dword ptr [rbp-28h],eax ss:000000001ca85ff8=00000000
0:013> k
# Child-SP          RetAddr               Call Site
00 000000001ca85fc0 00007ffa0cc6e2a9     ntdll!RtlpHeapFindListLookupEntry+0x52
01 000000001ca86060 00007ffa0cc76c15     ntdll!RtlpFindEntry+0x4d
02 000000001ca860a0 00007ffa0cc75b74     ntdll!RtlpFreeHeap+0x1015
03 000000001ca86250 00007ffa0cc747b1     ntdll!RtlpFreeHeapInternal+0x464
04 000000001ca86310 00007ffa0cd4952a     ntdll!RtlFreeHeap+0x51
05 000000001ca86350 00007ffa0cc75cc1     ntdll!RtlDebugFreeHeap+0x23e
06 000000001ca863b0 00007ffa0cc75b74     ntdll!RtlpFreeHeap+0xc1
07 000000001ca86560 00007ffa0cc747b1     ntdll!RtlpFreeHeapInternal+0x464
08 000000001ca86620 00007ff997ea8780     ntdll!RtlFreeHeap+0x51
09 000000001ca86660 00007ff997957a52     libPdfCore!CreateFactory+0x10162b0
0a 000000001ca86690 00007ff997957ec4     libPdfCore!CreateFactory+0xac5582
0b 000000001ca866d0 00007ff997957a70     libPdfCore!CreateFactory+0xac59f4
0c 000000001ca86700 00007ff997957ec4     libPdfCore!CreateFactory+0xac55a0
0d 000000001ca86740 00007ff997957a70     libPdfCore!CreateFactory+0xac59f4
0e 000000001ca86770 00007ff997957ec4     libPdfCore!CreateFactory+0xac55a0
0f 000000001ca867b0 00007ff997957a70     libPdfCore!CreateFactory+0xac59f4
10 000000001ca867e0 00007ff997957ec4     libPdfCore!CreateFactory+0xac55a0
11 000000001ca86820 00007ff997957a70     libPdfCore!CreateFactory+0xac59f4
12 000000001ca86850 00007ff997957ec4     libPdfCore!CreateFactory+0xac55a0
13 000000001ca86890 00007ff997957a70     libPdfCore!CreateFactory+0xac59f4
14 000000001ca868c0 00007ff997957ec4     libPdfCore!CreateFactory+0xac55a0
...
```

## Reference
[Wondershare PDF Reader](https://pdf.wondershare.com/pdf-reader.html)
