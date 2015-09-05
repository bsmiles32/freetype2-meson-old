project('freetype', 'c',
  version : '2.9.1',
  license : ['GPL2', 'freetype'])

cc = meson.get_compiler('c')

cdata = configuration_data()

incdir = include_directories('include')

subdir('src')

freetype_dep = declare_dependency(
    link_with: libfreetype,
    include_directories: incdir)

