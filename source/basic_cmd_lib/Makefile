#
# ingenic_boot configuration file
#
# Utility to respond to the Ingenic XBurst USB boot protocol, provide
# initial boot stages and ability to access NAND on device.
#
# Authors: Duke Fong <duke@dukelec.com>
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

CC := $(CROSS_COMPILE)gcc
CFLAGS := -fPIC -O2 -Wall

OBJS := basic_cmd_lib.o

ifdef STATIC
TARGET := ../../lib/libcmd.a
$(TARGET): $(OBJS)
	$(AR) rcs $@ $^
else
TARGET := ../../lib/libcmd.so
$(TARGET): $(OBJS)
	$(CC) -shared -o $@ $^
endif

.PHONY: all clean
all: $(TARGET)

clean:
	rm -rf $(TARGET) $(OBJS)
