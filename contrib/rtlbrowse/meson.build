definehash_c = custom_target(
    'definehash.c',
    input: 'vpp_keyword.gperf',
    output: 'definehash.c',
    command: [
        gperf,
        '-C',
        '-I',
        '-N', 'is_builtin_define',
        '--output-file', '@OUTPUT@',
        '@INPUT@',
    ],
)

vlex_c = flex_gen.process('vlex.l')

rtlbrowse_sources = [
    'fgetdynamic.c',
    'fgetdynamic.h',
    'jrb.c',
    'logfile.c',
    'main.c',
    'splay.c',
    'stem_recurse.c',
    'tree_widget.c',
    'gwr-model.c',
]

rtlbrowse_dependencies = [
    gtk4_dep,
    libfst_dep,
    libvzt_dep,
    liblxt_dep,
    libgtkwave_dep,
]

rtlbrowse_include_directories = [
    config_inc,
    '..',
]

executable(
    'rtlbrowse',
    rtlbrowse_sources,
    definehash_c,
    vlex_c,
    dependencies: rtlbrowse_dependencies,
    include_directories: rtlbrowse_include_directories,
    install: true,
)
