CXX = clang++

main: main.cpp
	$(CXX) -o main main.cpp

.PHONY: install
install: main
	mkdir -p $(PREFIX)/bin/
	cp -L main $(PREFIX)/bin/

