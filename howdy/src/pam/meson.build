project('pam_howdy', 'cpp', version: '0.1.0', default_options: ['cpp_std=c++14'])

inih_cpp = dependency('INIReader', fallback: ['inih', 'INIReader_dep'])
libevdev = dependency('libevdev')
libpam = meson.get_compiler('cpp').find_library('pam')
threads = dependency('threads')

# Translations
subdir('po')

shared_library(
	'pam_howdy',
	'main.cc',
	'enter_device.cc',
	dependencies: [
		libpam,
		inih_cpp,
		threads,
		libevdev,
	],
	install: true,
	install_dir: '/lib/security',
	name_prefix: ''
)
