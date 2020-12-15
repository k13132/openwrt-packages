%.o: %.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(FPIC) -Wall -c -o $@ $<

clean:
	rm -f luci-bwc *.o

luci-bwc: luci-bwc.o
	$(CC) $(LDFLAGS) -o $@ $^ -ldl

compile: luci-bwc

clean:
	rm -f luci-bwc *.o
