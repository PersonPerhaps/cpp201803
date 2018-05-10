CC = g++
CC_FLAGS = -W -Wall -Werror -I./
EXEC = my_bin
OBJS = main.o print.o

$(EXEC): $(OBJS)
	$(CC) $(CC_FLAGS) $(OBJS) -o $@

main.o: main.cpp
	$(CC) $(CC_FLAGS) -c -o $@ main.cpp

print.o: print.cpp print.hpp
	$(CC) $(CC_FLAGS) -c -o $@ print.cpp

all: $(EXEC)

clean:
	rm -rf $(OBJS) $(EXEC)
