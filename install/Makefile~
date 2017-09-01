EXEC_DIR = /home/dxg/helloworld
TARGET = HelloWorld

install: $(if $(wildcard $(TARGET)), install_$(TARGET))
uninstall: 
	rm $(EXEC_DIR)/$(TAEGET)
install_$(TARGET):
	@install -d $(EXEC_DIR)
	@install $(TARGET) $(EXEC_DIR)
	@install $(TARGET).txt $(EXEC_DIR)
	@echo
	@echo Installed $(TARGET) binaries to $(EXEC_DIR)..


