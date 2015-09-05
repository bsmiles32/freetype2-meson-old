subdir('autofit')
subdir('base')
subdir('bdf')
subdir('bzip2')
subdir('cache')
subdir('cff')
subdir('cid')
subdir('gzip')
subdir('lzw')
subdir('pcf')
subdir('pfr')
subdir('psaux')
subdir('pshinter')
subdir('psnames')
subdir('raster')
subdir('sfnt')
subdir('smooth')
subdir('truetype')
subdir('type1')
subdir('type42')
subdir('winfonts')

libfreetype_version = '6.16.0'

# ftconfig file generation
cdata.set('HAVE_UNISTD_H', cc.has_header('unistd.h'))
cdata.set('HAVE_FCNTL_H', cc.has_header('fcntl.h'))
cdata.set('HAVE_STDINT_H', cc.has_header('stdint.h'))

configure_file(
    input: '../builds/meson/ftconfig.in',
    output: 'ftconfig.h',
    configuration: cdata)


build_flags = ['-DFT2_BUILD_LIBRARY']

# get rid of msvc specific warnings regarding "non-standard" stuff
if cc.get_id() == 'msvc'
    build_flags += ['-D_CRT_SECURE_NO_WARNINGS', '-D_CRT_NONSTDC_NO_WARNINGS']
endif

libfreetype = library('freetype',
  [
    autofit_src,
    base_src,
    bdf_src,
    bzip2_src,
    cache_src,
    cff_src,
    cid_src,
    gzip_src,
    lzw_src,
    pcf_src,
    pfr_src,
    psaux_src,
    pshinter_src,
    psnames_src,
    raster_src,
    sfnt_src,
    smooth_src,
    truetype_src,
    type1_src,
    type42_src,
    winfonts_src
  ],
# need meson 0.48
# gnu_symbol_visibility : hidden,
  include_directories: incdir,
  c_args: build_flags,
  version : libfreetype_version)
