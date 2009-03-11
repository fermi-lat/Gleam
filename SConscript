# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/Gleam/SConscript,v 1.12 2009/02/06 23:30:12 glastrm Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-07-04-00
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

#Gleam = progEnv.GaudiProgram('Gleam',[' '],test=0) 
test_Gleam = progEnv.GaudiProgram('test_Gleam', listFiles(['src/test/*.cxx']), test=1)
progEnv.Tool('registerObjects', package = 'Gleam', 
	includes = listFiles(['Gleam/*.h']))




