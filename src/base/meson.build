# base layer sources
# ftsystem, ftinit and ftdebug can be overrided per-platform
base_src = [
    'base/ftbase.c',
    'base/ftbbox.c',
    'base/ftbdf.c',
    'base/ftbitmap.c',
    'base/ftcid.c',
    'base/ftfstype.c',
    'base/ftgasp.c',
    'base/ftglyph.c',
    'base/ftgxval.c',
    'base/ftinit.c',
    'base/ftmm.c',
    'base/ftotval.c',
    'base/ftpatent.c',
    'base/ftpfr.c',
    'base/ftstroke.c',
    'base/ftsynth.c',
    'base/fttype1.c',
    'base/ftwinfnt.c',
    'base/md5.c'
    ]

# ftsystem component
ftsys_src = ['base/ftsystem.c']
if host_machine.system() == 'linux'
    ftsys_src = ['../builds/unix/ftsystem.c']
endif
base_src += ftsys_src

# ftdebug component
ftdebug_src = ['base/ftdebug.c']
if host_machine.system() == 'windows'
    ftdebug_src = '../builds/windows/ftdebug.c'
endif
base_src += ftdebug_src

# ftinit component
ftinit_src = ['base/ftinit.c']
base_src += ftinit_src

# ftver component
if host_machine.system() == 'windows'
    win = import('windows')
    ftver_src = files('ftver.rc')
    base_src += win.compile_resources(ftver_src)
endif
