CXX = clang++
CXXWARNINGS = -Wall -Wshadow -Wuninitialized -Wtype-limits -Wno-unused-variable
CXXFLAGS = -std=gnu++20 -g -fsanitize=address,undefined $(CXXWARNINGS)
INCLUDEFLAGS = -I/usr/lib/llvm-18/include
LDFLAGS = -lclang -L/usr/lib/llvm-18/lib -rpath /usr/lib/llvm-18/lib -fuse-ld=lld

main: main.cpp plagiarism_checker.cpp tokenizer.cpp
	$(CXX) $(CXXFLAGS) $(INCLUDEFLAGS) $(LDFLAGS) $^ -o $@
	rm -rf *.dSYM
	ASAN_OPTIONS=detect_leaks=0 ./main hogwarts > output.txt
	diff -Bw hogwarts/expected.txt output.txt
	ASAN_OPTIONS=detect_leaks=0 ./main ainur > output1.txt
	diff -Bw ainur/expected.txt output1.txt

clean:
	rm -rf main output.txt output1.txt *.dSYM

.PHONY: main clean
