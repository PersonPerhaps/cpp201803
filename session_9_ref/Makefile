CC = g++
CC_FLAGS = -W -Wall -Werror
EXEC = my_bin
OBJS = main.o

all: $(EXEC)

$(EXEC): $(OBJS)
	$(CC) $(CC_FLAGS) $(OBJS) -o $@

main.o: main.cpp
	$(CC) $(CC_FLAGS) -c -o $@ main.cpp

clean:
	rm -rf $(OBJS) $(EXEC)
