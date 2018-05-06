project(
	'mako',
	'c',
	version: '0.0.0',
	license: 'MIT',
	meson_version: '>=0.43.0',
	default_options: [
		'c_std=c11',
		'warning_level=2',
		'werror=true',
	],
)

add_project_arguments('-Wno-unused-parameter', language: 'c')

mako_inc = include_directories('include')

cairo = dependency('cairo')
libsystemd = dependency('libsystemd')
pango = dependency('pango')
pangocairo = dependency('pangocairo')
wayland_client = dependency('wayland-client')
wayland_protos = dependency('wayland-protocols')

subdir('protocol')

executable(
	'mako',
	files([
		'dbus.c',
		'main.c',
		'pango.c',
		'pool-buffer.c',
		'render.c',
		'wayland.c',
	]),
	dependencies: [
		cairo,
		client_protos,
		libsystemd,
		pango,
		pangocairo,
		wayland_client,
	],
	include_directories: [mako_inc],
	install: true,
)