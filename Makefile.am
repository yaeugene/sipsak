ACLOCAL_AMFLAGS = -I m4

CC = ${DISTCC} @CC@

bin_PROGRAMS = sipsak

TRANSPORT_SOURCES = src/transport.c src/transport.h

sipsak_SOURCES = $(TRANSPORT_SOURCES) src/auth.c src/auth.h src/header_f.c src/header_f.h src/helper.c src/helper.h src/md5.c src/md5.h src/md5global.h src/request.c src/request.h src/shoot.c src/shoot.h src/sipsak.c src/sipsak.h src/exit_code.h src/exit_code.c

dist_man1_MANS=sipsak.1

# Tests

TESTS = tests/check_helper tests/check_md5

check_PROGRAMS = $(TESTS)

tests_check_helper_SOURCES = tests/check_helper.c src/helper.h src/helper.c src/exit_code.h src/exit_code.c
tests_check_helper_CFLAGS = @CHECK_CFLAGS@ -DRUNNING_CHECK
tests_check_helper_LDADD = @CHECK_LIBS@

tests_check_md5_SOURCES = tests/check_md5.c src/md5.h src/md5.c
tests_check_md5_CFLAGS = @CHECK_CFLAGS@ -DRUNNING_CHECK
tests_check_md5_LDADD = @CHECK_LIBS@

FAKE_TRANSPORT_SOURCES = tests/fake_transport.c src/transport.h
