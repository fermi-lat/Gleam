# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/Gleam/SConscript,v 1.89 2014/04/08 22:30:36 glastrm Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-08-00-07
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
                             'src/jobOptions/simulations/*.txt',
			     'src/jobOptions/pipeline/*.txt']) )





