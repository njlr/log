include_defs('//BUCKAROO_DEPS')

windows_srcs = glob([
  'src/windows/**/*.cpp',
])

posix_srcs = glob([
  'src/posix/**/*.cpp',
])

linux_srcs = posix_srcs

macos_srcs = posix_srcs

platform_srcs = windows_srcs + posix_srcs

cxx_library(
  name = 'log',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', '**/*.hpp'),
  ]),
  headers = subdir_glob([
    ('src', '**/*.hpp'),
  ]),
  srcs = glob([
    'src/**/*.cpp',
  ], excludes = platform_srcs),
  platform_srcs = [
    ('default', linux_srcs),
    ('^linux.*', linux_srcs),
    ('^macos.*', macos_srcs),
    ('^windows.*', windows_srcs),
  ],
  deps = BUCKAROO_DEPS,
  visibility = [
    'PUBLIC',
  ],
)
