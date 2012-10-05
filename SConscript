# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/Gleam/SConscript,v 1.66 2012/10/05 19:03:26 heather Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-07-11-11
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
progEnv.Tool('configDataLib')
progEnv.Tool('RootConvertLib')
progEnv.Tool('rootUtilLib')
progEnv.Tool('GlastClassifyLib')
progEnvTest = progEnv.Clone()

Gleam = progEnv.GaudiProgram('Gleam',[],test=0, package='Gleam') 
test_Gleam = progEnvTest.GaudiProgram('test_Gleam', listFiles(['src/test/*.cxx']),
				  test=1, package='Gleam')
progEnv.Tool('registerTargets', package = 'Gleam', 
	     testAppCxts = [[test_Gleam, progEnvTest]],
	     binaryCxts = [[Gleam, progEnv]],
         data = ['data/dummy.txt'],
	     jo = listFiles(['src/*.txt', 'src/test/*.txt',
			     'src/jobOptions/pipeline/*.txt']) )





