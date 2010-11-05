# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/Gleam/SConscript,v 1.27 2010/09/24 00:21:51 lsrea Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-07-06-00
Import('baseEnv')
Import('listFiles')
Import('packages')
progEnv = baseEnv.Clone()
libEnv = baseEnv.Clone()

progEnv.Tool('GuiSvcLib')
progEnv.Tool('guiLib')
progEnv.Tool('xmlUtilLib')
progEnv.Tool('CalibDataLib')
progEnv.Tool('calibRootDataLib')
progEnv.Tool('overlayRootDataLib')
progEnv.Tool('CalUtilLib')
progEnv.Tool('ldfReaderLib')
progEnv.Tool('TMineLib')
progEnv.Tool('configDataLib')
progEnv.Tool('RootConvertLib')
progEnv.Tool('rootUtilLib')

if baseEnv['PLATFORM'] != 'win32':
	progEnv.AppendUnique(LINKFLAGS=['-u GuiSvc_loadRef'])
	progEnv.Tool('addLibrary', library = ['dl'])

if baseEnv['PLATFORM'] == 'win32':
	progEnv.AppendUnique(LINKFLAGS = ['/include:_GuiSvc_loadRef'])

# Add dependencies for all shareable, non-component libraries
#progEnv.Tool('addLibrary',
#	     library= ['facilities','xmlBase', 'xmlUtil', 'CalUtil','astro',
#		       'CalibData', 'Event','OverlayEvent', 'OnboardFilterTds',
#		       'rootUtil','rdbModel', 'calibUtil', 'mootCore',
#		       'commonRootData', 'digiRootData', 'reconRootData',
#		       'calibRootData', 'mcRootData', 'overlayRootData', 
#		       'gcrSelectRootData', 'RootConvert', 'eventFile',
#		       'lsfData', 'ldfReader','TMine','configData'])
		       
		     

Gleam = progEnv.GaudiProgram('Gleam',[],test=0, package='Gleam') 
test_Gleam = progEnv.GaudiProgram('test_Gleam', listFiles(['src/test/*.cxx']),
				  test=1, package='Gleam')
progEnv.Tool('registerTargets', package = 'Gleam', 
	     testAppCxts = [[test_Gleam, progEnv]],
	     binaryCxts = [[Gleam, progEnv]],
	     jo = listFiles(['src/*.txt', 'src/test/*.txt',
			     'src/jobOptions/pipeline/*.txt']) )





