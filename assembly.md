C++语言
	__Z3foov:                               ## @_Z3foov
		.cfi_startproc
	## BB#0:
		pushq	%rbp
	Ltmp2:
			.cfi_def_cfa_offset 16
	Ltmp3:
		.cfi_offset %rbp, -16
		movq	%rsp, %rbp
	Ltmp4:
		.cfi_def_cfa_register %rbp
		movl	$100, %eax
		movl	$1000, -4(%rbp)         ## imm = 0x3E8
		popq	%rbp
		ret
		.cfi_endproc
		
--------------------------
		
	int foo(){
		int x = 1000;
		return 100;
	}
	
-------------------------

__Z3fooi:

	int foo(int){
		int x = 1000;
		return 100;
	}
	
__Z3fooii:
	
	int foo(int,int ){
		int x = 1000;
		return 100;
	}

__Z8functionii;

	int foo(int, int){
		int x = 1000;
		return 100;
	}
	
------------
### What is  __8


