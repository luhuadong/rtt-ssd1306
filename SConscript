from building import *
Import('rtconfig')

src   = []
cwd   = GetCurrentDir()

# add ssd1306 src files.
if GetDepend('PKG_USING_SSD1306'):
    src += Glob('src/ssd1306.c')
    src += Glob('src/ssd1306_fonts.c')

if GetDepend('PKG_USING_SSD1306_SAMPLE'):
    src += Glob('examples/ssd1306_tests.c')

# add ssd1306 include path.
path  = [cwd + '/inc']

# add src and include to group.
group = DefineGroup('ssd1306', src, depend = ['PKG_USING_SSD1306'], CPPPATH = path)

Return('group')