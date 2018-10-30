
FILES = \
	WPS_original.lts \
	WPS_e.lts

TESTS = \
	mcf/2a.bool \
	mcf/2b.bool \
	mcf/3a.bool \
	mcf/3b.bool \
	mcf/4a.bool \
	mcf/4b.bool \
	mcf/5a.bool \
	mcf/5b.bool \
	mcf/6a.bool \
	mcf/6b.bool \
	mcf/7.bool \
	mcf/8a.bool \
	mcf/8b.bool \
	mcf/9.bool \
	mcf/10.bool \
	mcf/11a.bool \
    mcf/11b.bool \
    mcf/12.bool \
    mcf/13a.bool \
    mcf/13b.bool \
    mcf/14a.bool \
    mcf/14b.bool \
    mcf/15a.bool \
    mcf/15b.bool \
    mcf/16a.bool \
    mcf/16b.bool \
	mcf/17DeadlockFree.bool

all: $(FILES)
tests: $(TESTS)

graph: WPS_original.graph
graph-e: WPS_e.graph

sim: WPS_original.sim
sim-e: WPS_e.sim

view: WPS_original.view
view-e: WPS_e.view

%.lps: %.mcrl2
	mcrl22lps $< $@

%.lts: %.lps
	lps2lts $< $@

WPS_original.lts: WPS_original.lps
	lps2lts -rjittyc -v $< $@
WPS_e.lts: WPS_e.lps
	lps2lts -rjittyc -v $< $@

%.pbes: %.mcf WPS_e.lps
	lps2pbes -f$< WPS_e.lps $@
%.pbes-lps: %.mcf WPS_e.lps
	lps2pbes -f$< WPS_e.lps $@
%.pbes-lts: %.mcf WPS_e.lts
	lts2pbes -f$< WPS_e.lts $@

%.bool: %.pbes
	@date
	@echo -n "Running test $< ... "
	@pbes2bool $<
%.bool-lps: %.pbes-lps
	@date
	@echo -n "Running test $< ... "
	@pbes2bool $<
%.bool-lts: %.pbes-lts
	@date
	@echo -n "Running test $< ... "
	@pbes2bool $<

%.graph: %.lts
	ltsgraph $<

%.sim: %.lps
	lpsxsim $<

%.view: %.lts
	ltsview $<

clean:
	rm -f */*.lps *.lps
	rm -f */*.lts *.lts
	rm -f */*.pbes *.pbes
	rm -f jittyc_*

