%.o: %.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(FPIC) -c -o $@ $<


luci-bwc: luci-bwc.o
	$(CC) $(LDFLAGS) -o $@ $^ -ldl

clean:
	rm -f luci-bwc *.o

