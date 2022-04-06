Shared Library
=================


guess.c

.. code:: c

   #include <stdio.h>
   #include <stdlib.h>
   #include <time.h>
   #include <sys/types.h>
   #include <unistd.h>

   int main() {
       char buf[16];
       int answer;

       setvbuf(stdout, NULL, _IONBF, 0); 
       srand(time(0) ^ getpid());
       answer = rand() % 10000;

       printf("Guess the number: ");
       if(fgets(buf, 32, stdin) != NULL) {
               int g = strtol(buf, NULL, 0); 
               printf("Your guess is %d\n", g); 
               if(g == answer) {
                       printf("Bingo!\n");
               } else {
                       printf("No no no ...\n");
               }
       }   

       return 0;
   }



command

.. code:: sh

   gcc -S guess.c -masm=intel



guess.s

因為只有跑 compiler, 還沒跑 linker, 所以 addr 還沒有查

.. code:: assembly

           .file   "guess.c"
           .intel_syntax noprefix
           .text
           .section        .rodata
   .LC0:
           .string "Guess the number: "
   .LC1:
           .string "Your guess is %d\n"
   .LC2:
           .string "Bingo!"
   .LC3:
           .string "No no no ..."
           .text
           .globl  main
           .type   main, @function
   main:
   .LFB6:
           .cfi_startproc
           endbr64
           push    rbp
           .cfi_def_cfa_offset 16
           .cfi_offset 6, -16
           mov     rbp, rsp
           .cfi_def_cfa_register 6
           push    rbx
           sub     rsp, 56
           .cfi_offset 3, -24
           mov     rax, QWORD PTR fs:40
           mov     QWORD PTR -24[rbp], rax
           xor     eax, eax
           mov     rax, QWORD PTR stdout[rip]
           mov     ecx, 0
           mov     edx, 2
           mov     esi, 0
           mov     rdi, rax
           call    setvbuf@PLT
           mov     edi, 0
           call    time@PLT
           mov     ebx, eax
           call    getpid@PLT
           xor     eax, ebx
           mov     edi, eax
           call    srand@PLT
           call    rand@PLT
           movsx   rdx, eax
           imul    rdx, rdx, 1759218605
           shr     rdx, 32
           mov     ecx, edx
           sar     ecx, 12
           cdq
           sub     ecx, edx
           mov     edx, ecx
           mov     DWORD PTR -56[rbp], edx
           mov     edx, DWORD PTR -56[rbp]
           imul    edx, edx, 10000
           sub     eax, edx
           mov     DWORD PTR -56[rbp], eax
           lea     rdi, .LC0[rip]
           mov     eax, 0
           call    printf@PLT
           mov     rdx, QWORD PTR stdin[rip]
           lea     rax, -48[rbp]
           mov     esi, 32
           mov     rdi, rax
           call    fgets@PLT
           test    rax, rax
           je      .L2
           lea     rax, -48[rbp]
           mov     edx, 0
           mov     esi, 0
           mov     rdi, rax
           call    strtol@PLT
           mov     DWORD PTR -52[rbp], eax
           mov     eax, DWORD PTR -52[rbp]
           mov     esi, eax
           lea     rdi, .LC1[rip]
           mov     eax, 0
           call    printf@PLT
           mov     eax, DWORD PTR -52[rbp]
           cmp     eax, DWORD PTR -56[rbp]
           jne     .L3
           lea     rdi, .LC2[rip]
           call    puts@PLT
           jmp     .L2
   .L3:
           lea     rdi, .LC3[rip]
           call    puts@PLT
   .L2:
           mov     eax, 0
           mov     rbx, QWORD PTR -24[rbp]
           xor     rbx, QWORD PTR fs:40
           je      .L5
           call    __stack_chk_fail@PLT
   .L5:
           add     rsp, 56
           pop     rbx
           pop     rbp
           .cfi_def_cfa 7, 8
           ret
           .cfi_endproc
   .LFE6:
           .size   main, .-main
           .ident  "GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0"
           .section        .note.GNU-stack,"",@progbits
           .section        .note.gnu.property,"a"
           .align 8
           .long    1f - 0f
           .long    4f - 1f
           .long    5
   0:
           .string  "GNU"
   1:
           .align 8
           .long    0xc0000002
           .long    3f - 2f
   2:
           .long    0x3
   3:
           .align 8
   4:


|

查看真正的 addr
----------------

gcc -o 執行檔, 再用 objdump 反組譯, 指定用 intel 語法輸出, 再導到 guess.s


objdump -D 反組譯

.. code:: shell

   gcc -o guess -Wall -g -fno-stack-protector guess.c  
   objdump -D guess -M intel > guess.s

|

.. code:: shell

   gdb got
   
   gdb >> layout asm


