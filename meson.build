project(
  'video-editing-automation',
  'c',
  default_options: [
    'c_std=c2x',
    'warning_level=3',
  ]
)

avcodec = dependency('libavcodec')
avformat = dependency('libavformat')
avutil = dependency('libavutil')
swscale = dependency('libswscale')
swresample = dependency('libswresample')

inc = include_directories('include')

base = library(
  'automation-base',
  'src/Clip.c',
  'src/ClipDecode.c',
  'src/ClipEncode.c',
  'src/LinkedListAPI.c',
  'src/OutputContext.c',
  'src/Sequence.c',
  'src/SequenceDecode.c',
  'src/SequenceEncode.c',
  'src/Timebase.c',
  'src/Util.c',
  'src/VideoContext.c',
  include_directories: inc,
  install: true,
  dependencies: [avcodec, avformat, avutil, swscale, swresample],
)

base_dep = declare_dependency(
  link_with: base,
  include_directories: inc,
  dependencies: [avcodec, avformat, avutil, swscale, swresample],
)

subdir('examples')
