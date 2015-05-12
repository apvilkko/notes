# Developing on Windows - Quirks

## nosetests doesn't find tests (Python)

**Problem**: You'll get `Ran 0 tests` although there should be tests that match.

**Reason**: Nose skips files that are in executable mode. This might be the case if you are developing in a virtual machine and your sources are shared from host. The default mount on VirtualBox sets all files as `+x`.

**Solution**: Add `--exe` to `nosetests` command. This inverts the matching so that only executables files are matched.

## npm install fails (node)

**Problem**: Installing a node module fails.

**Reason**: Symbolic links (usually).

**Solution**: Add `--no-bin-links` to `npm install` command
