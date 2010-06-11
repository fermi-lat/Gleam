# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/GlastRelease-scons/Gleam/SConscript,v 1.21 2010/04/21 15:37:02 lsrea Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-07-04-08
Import('baseEnv')
Import('listFiles')
Import('packages')
progEnv = baseEnv.Clone()
libEnv = baseEnv.Clone()

progEnv.Tool('GuiSvcLib')
progEnv.Tool('guiLib')

if baseEnv['PLATFORM'] != 'win32':
	progEnv.AppendUnique(LINKFLAGS=['-u GuiSvc_loadRef'])
	progEnv.Tool('addLibrary', library = ['dl'])

if baseEnv['PLATFORM'] == 'win32':
	progEnv.AppendUnique(LINKFLAGS = ['/include:_GuiSvc_loadRef'])

Gleam = progEnv.GaudiProgram('Gleam',[],test=0, package='Gleam') 
test_Gleam = progEnv.GaudiProgram('test_Gleam', listFiles(['src/test/*.cxx']),
				  test=1, package='Gleam')
progEnv.Tool('registerTargets', package = 'Gleam', 
	     testAppCxts = [[test_Gleam, progEnv]],
	     binaryCxts = [[Gleam, progEnv]],
	     jo = listFiles(['src/*.txt', 'src/test/*.txt',
			     'src/jobOptions/pipeline/*.txt']) )





