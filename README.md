section .data
    hello db 'hallo semuanya',0

section .text
    global _start

_start:
    ; Write the text to stdout
    mov eax, 4        ; sys_write
    mov ebx, 1        ; file descriptor 1 (stdout)
    mov ecx, hello    ; pointer to the message
    mov edx, 14       ; message length
    int 0x80          ; invoke syscall

    ; Exit the program
    mov eax, 1        ; sys_exit
    xor ebx, ebx      ; exit status
    int 0x80          ; invoke syscall
