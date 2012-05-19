CC = gcc
CFLAGS := `pkg-config --cflags libpcsclite` $(CFLAGS)
LDFLAGS := `pkg-config --libs libpcsclite` $(LDFLAGS)

all: casinfo

casinfo.o: casinfo.c portable.h b_cas_card.h b_cas_card_error_code.h broadcast_service.h arib_util.h
	$(CC) -c $(CFLAGS) casinfo.c

b_cas_card.o: b_cas_card.c b_cas_card.h portable.h b_cas_card_error_code.h arib_util.h
	$(CC) -c $(CFLAGS) b_cas_card.c

OBJ = casinfo.o b_cas_card.o

casinfo: $(OBJ)
	$(CC) $(LDFLAGS) -o casinfo $(OBJ)

clean:
	$(RM) *.o casinfo
