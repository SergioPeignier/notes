python -m cProfile -o profile.pstats kymeroChameleo.py
gprof2dot -f pstats profile.pstats | dot -Tpng -o prof.png
