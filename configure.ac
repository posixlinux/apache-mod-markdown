# Required initializer
AC_INIT(apache-mod-markdown, 1.0.2)

# Automake initialization
AM_INIT_AUTOMAKE([dist-bzip2 foreign])
AM_CONFIG_HEADER(config.h)

# Add a test for a compiler.
AC_PROG_CC
AM_PROG_LIBTOOL

AC_CONFIG_MACRO_DIR([m4])
AX_CHECK_COMPILE_FLAG([-Wall], [CFLAGS="$CFLAGS -Wall"], [], [])

AC_ARG_WITH(apxs,
            [  --with-apxs=FILE      pathname to the Apache apxs tool ],
            ,[with_apxs="/usr/bin/apxs"])
AC_MSG_CHECKING(for apxs tool)
if test -e $with_apxs; then
    apxs=$with_apxs
    AC_MSG_RESULT(APXS found!)
else
    AC_MSG_ERROR( $with_apxs not found.  Check the value you specified with --with-apxs)
fi
AC_SUBST(apxs)

AC_ARG_WITH(discount, [  --with-discount=DIR    discount directory ],,[with_discount="/usr"])
AC_MSG_CHECKING(for discount directory)
if test -e $with_discount/include/mkdio.h -o -e $with_discount/include/*/mkdio.h; then
    discount_dir=$with_discount
    AC_MSG_RESULT(DISCOUNT found!)
else
    AC_MSG_ERROR( $with_discount not found.  Check the value you specified with --with-discount)
fi
AC_SUBST(discount_dir)

# Write config.status and the Makefile
AC_OUTPUT(Makefile)
