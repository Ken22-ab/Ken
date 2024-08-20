
import { render, Instance } from 'ink'
import meow from 'meow'
import mls from 'multilines'
import ora from 'ora'
import updateNotifier from 'update-notifier'
import prompts from 'prompts'

import { IStarter } from './algolia'
import Emma from './Emma'
import { getDistDirectory, getStarterTemplateRepo } from './installer'
import { drawBox } from './structure'
import { mkdirSync } from 'fs'

/* Spec */

const cli = meow(
  mls`
  | Usage
  |  $ create-emma <dir>
  `,
)

/**
 * Make sure that user is on the latest version
 * avaiable in case they have connection to NPM.
 */

const notifier = updateNotifier(cli)

notifier.notify()

if (notifier.update) {</dir>
