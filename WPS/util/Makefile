#	WPS component makefile

include ../configure.wps

bad_idea:
	clear ;
	@echo " "
	@echo " "
	@echo "go up a directory and type 'compile' to build WPS"
	@echo " "
	@echo " "

all:
	( cd src ; \
	$(MAKE) $(TARGET) \
		WRF_DIR="$(WRF_DIR_PRE)$(WRF_DIR)" \
		FC="$(FC)" \
		CC="$(CC)" \
		CPP="$(CPP)" \
		FFLAGS="$(FFLAGS)" \
		CFLAGS="$(CFLAGS)" \
		LDFLAGS="$(LDFLAGS)" \
		CPPFLAGS="$(CPPFLAGS) -D_$(CPP_TARGET)" )
	if [ -h $(TARGET) ] ; then \
		$(RM) $(TARGET) ; \
	fi ; \
	if [ -h ../$(TARGET) ] ; then \
		$(RM) ../$(TARGET) ; \
	fi ; \
	if [ -e src/$(TARGET) ] ; then \
		$(LN) src/$(TARGET) . ; \
	fi

clean:
	if [ -h $(TARGET) ] ; then \
		$(RM) $(TARGET) ; \
	fi
	if [ -h ../$(TARGET) ] ; then \
		$(RM) ../$(TARGET) ; \
	fi
	( cd src ; $(MAKE) clean )

superclean: clean
