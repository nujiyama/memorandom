# AlmaLinux 8にNeovimをインストールする

参考： [neovim/INSTALL.md at master · neovim/neovim](https://github.com/neovim/neovim/blob/master/INSTALL.md)

```bash
$ sudo dnf install epel-release
$ sudo dnf install neovim python3-neovim
$ which nvim
/usr/bin/nvim
$ nvim -v
NVIM v0.8.0
Build type: RelWithDebInfo
LuaJIT 2.1.0-beta3
Compilation: /usr/bin/cc -O2 -g -pipe -Wall -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -Wp,-D_GLIBCXX_ASSERTIONS -fexceptions -fstack-protector-strong -grecord-gcc-switches -specs=/usr/lib/rpm/redhat/redhat-hardened-cc1 -specs=/usr/lib/rpm/redhat/redhat-annobin-cc1 -m64 -mtune=generic -fasynchronous-unwind-tables -fstack-clash-protection -fcf-protection -Wp,-U_FORTIFY_SOURCE -Wp,-D_FORTIFY_SOURCE=1 -DNVIM_TS_HAS_SET_MATCH_LIMIT -DNVIM_TS_HAS_SET_ALLOCATOR -O2 -g -Og -g -Wall -Wextra -pedantic -Wno-unused-parameter -Wstrict-prototypes -std=gnu99 -Wshadow -Wconversion -Wdouble-promotion -Wmissing-noreturn -Wmissing-format-attribute -Wmissing-prototypes -Wimplicit-fallthrough -Wvla -fstack-protector-strong -fno-common -fdiagnostics-color=auto -DINCLUDE_GENERATED_DECLARATIONS -D_GNU_SOURCE -DNVIM_MSGPACK_HAS_FLOAT32 -DNVIM_UNIBI_HAS_VAR_FROM -DMIN_LOG_LEVEL=3 -I/builddir/build/BUILD/neovim-0.8.0/x86_64-redhat-linux-gnu/cmake.config -I/builddir/build/BUILD/neovim-0.8.0/src -I/usr/include -I/usr/include/luajit-2.1 -I/builddir/build/BUILD/neovim-0.8.0/x86_64-redhat-linux-gnu/src/nvim/auto -I/builddir/build/BUILD/neovim-0.8.0/x86_64-redhat-linux-gnu/include
Compiled by mockbuild@koji

Features: +acl +iconv +tui
See ":help feature-compile"

   system vimrc file: "$VIM/sysinit.vim"
  fall-back for $VIM: "/usr/share/nvim"

Run :checkhealth for more info
$
```
