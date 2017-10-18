VENDOR=Blinkinlabs
PROJECT_NAME=BlinkyPendant
VERSION=3.00
DOWNLOAD_ROOT=https://github.com/Blinkinlabs/BlinkyPendant/raw/master/bin
FIRMWARE_FILE=pendant-firmware-v300.dfu
METAINFO_FILE=BlinkyPendant.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

$(FIRMWARE_FILE):
	wget $(DOWNLOAD_ROOT)/$@ -O $@

clean:
	rm -f *.cab *.dfu

check: $(METAINFO_FILE)
	appstream-util validate-relax $(METAINFO_FILE)

%.cab: $(FIRMWARE_FILE) $(METAINFO_FILE)
	gcab --create --nopath $@ $(FIRMWARE_FILE) $(METAINFO_FILE)
