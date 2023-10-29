    section .data
        hello db 'hallo semuanya',0

    section .text
        global _start

    _start:
        ; Write the text to stdout
        mov ebx, 1        ; file descriptor 1 (stdout)
        mov ecx, hello    ; pointer to the message
        int 0x80          ; invoke syscall

    ; Exit the program
        xor ebx, ebx      ; exit status
        int 0x80          ; invoke syscall
