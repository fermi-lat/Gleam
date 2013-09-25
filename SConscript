# -*- python -*-
# $Header: /nfs/slac/g/glast/ground/cvs/Gleam/SConscript,v 1.20.2.9.2.4 2013/09/19 18:40:16 heather Exp $
# Authors: T. Burnett <tburnett@u.washington.edu>
# Version: Gleam-07-04-07-gr15
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

Gleam = progEnv.GaudiProgram('Gleam',[],test=0, package='Gleam') 
test_Gleam = progEnv.GaudiProgram('test_Gleam', listFiles(['src/test/*.cxx']),
				  test=1, package='Gleam')
progEnv.Tool('registerTargets', package = 'Gleam', 
	     testAppCxts = [[test_Gleam, progEnv]],
	     binaryCxts = [[Gleam, progEnv]],
         data = ['data/dummy.txt'],
	     jo = listFiles(['src/*.txt', 'src/test/*.txt',
			     'src/jobOptions/pipeline/*.txt']) )





