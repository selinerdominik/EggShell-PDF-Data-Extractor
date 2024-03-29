#========================================================================
#
# Xpdf Makefile
#
# Copyright 1996-2003 Glyph & Cog, LLC
#
#========================================================================

SHELL = /bin/sh

prefix = /usr/local
srcdir = .


GOOSRCDIR = $(srcdir)/../goo
GOOLIBDIR = ../goo
FOFISRCDIR = $(srcdir)/../fofi
FOFILIBDIR = ../fofi
SPLASHSRCDIR = $(srcdir)/../splash
SPLASHLIBDIR = ../splash

CXXFLAGS = -g -O2 -DHAVE_CONFIG_H -I.. -I$(srcdir)/.. -I$(GOOSRCDIR) -I$(FOFISRCDIR) -I$(SPLASHSRCDIR) -I$(srcdir) -I/usr//local/include/freetype2          

LDFLAGS = 

FTLIBS = -L/usr//local/Library/LinkedKegs/freetype -lfreetype -lz

XLIBS =         -lX11 

PNGLIBS = -lpng

SPLASHLIBS = -L$(SPLASHLIBDIR) -lsplash

OTHERLIBS =    \
	-L$(FOFILIBDIR) -lfofi \
	-L$(GOOLIBDIR) -lGoo

CXX = g++

LIBPREFIX = lib
EXE = 

#------------------------------------------------------------------------

.SUFFIXES: .cc

.cc.o:
	$(CXX) $(CXXFLAGS) -c $<

#------------------------------------------------------------------------

CXX_SRC = \
	$(srcdir)/AcroForm.cc \
	$(srcdir)/Annot.cc \
	$(srcdir)/Array.cc \
	$(srcdir)/BuiltinFont.cc \
	$(srcdir)/BuiltinFontTables.cc \
	$(srcdir)/CMap.cc \
	$(srcdir)/Catalog.cc \
	$(srcdir)/CharCodeToUnicode.cc \
	$(srcdir)/CoreOutputDev.cc \
	$(srcdir)/Decrypt.cc \
	$(srcdir)/Dict.cc \
	$(srcdir)/Error.cc \
	$(srcdir)/FontEncodingTables.cc \
	$(srcdir)/Form.cc \
	$(srcdir)/Function.cc \
	$(srcdir)/Gfx.cc \
	$(srcdir)/GfxFont.cc \
	$(srcdir)/GfxState.cc \
	$(srcdir)/GlobalParams.cc \
	$(srcdir)/HTMLGen.cc \
	$(srcdir)/ImageOutputDev.cc \
	$(srcdir)/JArithmeticDecoder.cc \
	$(srcdir)/JBIG2Stream.cc \
	$(srcdir)/JPXStream.cc \
	$(srcdir)/Lexer.cc \
	$(srcdir)/Link.cc \
	$(srcdir)/NameToCharCode.cc \
	$(srcdir)/Object.cc \
	$(srcdir)/OptionalContent.cc \
	$(srcdir)/Outline.cc \
	$(srcdir)/OutputDev.cc \
	$(srcdir)/PDFCore.cc \
	$(srcdir)/PDFDoc.cc \
	$(srcdir)/PDFDocEncoding.cc \
	$(srcdir)/PSOutputDev.cc \
	$(srcdir)/PSTokenizer.cc \
	$(srcdir)/Page.cc \
	$(srcdir)/Parser.cc \
	$(srcdir)/PreScanOutputDev.cc \
	$(srcdir)/SecurityHandler.cc \
	$(srcdir)/SplashOutputDev.cc \
	$(srcdir)/Stream.cc \
	$(srcdir)/TextOutputDev.cc \
	$(srcdir)/TextString.cc \
	$(srcdir)/UnicodeMap.cc \
	$(srcdir)/UnicodeTypeTable.cc \
	$(srcdir)/XFAForm.cc \
	$(srcdir)/XPDFApp.cc \
	$(srcdir)/XPDFCore.cc \
	$(srcdir)/XPDFTree.cc \
	$(srcdir)/XPDFViewer.cc \
	$(srcdir)/XpdfPluginAPI.cc \
	$(srcdir)/XRef.cc \
	$(srcdir)/Zoox.cc \
	$(srcdir)/pdftops.cc \
	$(srcdir)/pdftotext.cc \
	$(srcdir)/pdftoxml.cc \
	$(srcdir)/pdfinfo.cc \
	$(srcdir)/pdffonts.cc \
	$(srcdir)/pdfdetach.cc \
	$(srcdir)/pdftoppm.cc \
	$(srcdir)/pdftopng.cc \
	$(srcdir)/pdfimages.cc \
	$(srcdir)/xpdf.cc

#------------------------------------------------------------------------

all: xpdf$(EXE) pdftops$(EXE) pdftotext$(EXE) pdftoxml$(EXE) \
	pdfinfo$(EXE) pdffonts$(EXE) pdfdetach$(EXE) pdftoppm$(EXE) \
	pdftopng$(EXE) pdfimages$(EXE)

all-no-x: pdftops$(EXE) pdftotext$(EXE) pdftoxml$(EXE) pdfinfo$(EXE) \
	pdffonts$(EXE) pdfdetach$(EXE) pdfimages$(EXE)

#------------------------------------------------------------------------

XPDF_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	CoreOutputDev.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFCore.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PreScanOutputDev.o \
	PSOutputDev.o \
	PSTokenizer.o \
	SecurityHandler.o \
	SplashOutputDev.o \
	Stream.o \
	TextOutputDev.o \
	TextString.o \
	UnicodeMap.o \
	UnicodeTypeTable.o \
	XFAForm.o \
	XPDFApp.o \
	XPDFCore.o \
	XPDFTree.o \
	XPDFViewer.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	xpdf.o
XPDF_LIBS = -L$(GOOLIBDIR) -lGoo $(SPLASHLIBS) $(FTLIBS) \
	$(XLIBS) $(OTHERLIBS) -lm

xpdf$(EXE): $(XPDF_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o xpdf$(EXE) $(XPDF_OBJS) $(XPDF_LIBS)

#------------------------------------------------------------------------

PDFTOPS_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	OptionalContent.o \
	Outline.o \
	Object.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PreScanOutputDev.o \
	PSOutputDev.o \
	PSTokenizer.o \
	SecurityHandler.o \
	SplashOutputDev.o \
	Stream.o \
	TextString.o \
	UnicodeMap.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdftops.o
PDFTOPS_LIBS = -L$(GOOLIBDIR) -lGoo $(SPLASHLIBS) $(FTLIBS) \
	$(OTHERLIBS) -lm

pdftops$(EXE): $(PDFTOPS_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdftops$(EXE) $(PDFTOPS_OBJS) \
		$(PDFTOPS_LIBS)

#------------------------------------------------------------------------

PDFTOTEXT_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	Stream.o \
	TextOutputDev.o \
	TextString.o \
	UnicodeMap.o \
	UnicodeTypeTable.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdftotext.o
PDFTOTEXT_LIBS = -L$(GOOLIBDIR) -lGoo $(OTHERLIBS) -lm

pdftotext$(EXE): $(PDFTOTEXT_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdftotext$(EXE) $(PDFTOTEXT_OBJS) \
		$(PDFTOTEXT_LIBS)

#------------------------------------------------------------------------

pdftoxml_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	HTMLGen.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	SplashOutputDev.o \
	Stream.o \
	TextOutputDev.o \
	TextString.o \
	UnicodeMap.o \
	UnicodeTypeTable.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdftoxml.o
pdftoxml_LIBS = -L$(GOOLIBDIR) -lGoo $(SPLASHLIBS) $(FTLIBS) \
	$(OTHERLIBS) $(PNGLIBS) -lm

pdftoxml$(EXE): $(pdftoxml_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdftoxml$(EXE) $(pdftoxml_OBJS) \
		$(pdftoxml_LIBS)

#------------------------------------------------------------------------

PDFINFO_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	Stream.o \
	TextString.o \
	UnicodeMap.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdfinfo.o
PDFINFO_LIBS = -L$(GOOLIBDIR) -lGoo $(OTHERLIBS) -lm

pdfinfo$(EXE): $(PDFINFO_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdfinfo$(EXE) $(PDFINFO_OBJS) \
		$(PDFINFO_LIBS)

#------------------------------------------------------------------------

PDFFONTS_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	Stream.o \
	TextString.o \
	UnicodeMap.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdffonts.o
PDFFONTS_LIBS = -L$(GOOLIBDIR) -lGoo $(OTHERLIBS) -lm

pdffonts$(EXE): $(PDFFONTS_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdffonts$(EXE) $(PDFFONTS_OBJS) \
		$(PDFFONTS_LIBS)

#------------------------------------------------------------------------

PDFDETACH_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	Stream.o \
	TextString.o \
	UnicodeMap.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdfdetach.o
PDFDETACH_LIBS = -L$(GOOLIBDIR) -lGoo $(OTHERLIBS) -lm

pdfdetach$(EXE): $(PDFDETACH_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdfdetach$(EXE) $(PDFDETACH_OBJS) \
		$(PDFDETACH_LIBS)

#------------------------------------------------------------------------

PDFTOPPM_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	SplashOutputDev.o \
	Stream.o \
	TextOutputDev.o \
	TextString.o \
	UnicodeMap.o \
	UnicodeTypeTable.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdftoppm.o
PDFTOPPM_LIBS = -L$(GOOLIBDIR) -lGoo $(SPLASHLIBS) $(FTLIBS) \
	$(OTHERLIBS) -lm

pdftoppm$(EXE): $(PDFTOPPM_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdftoppm$(EXE) $(PDFTOPPM_OBJS) \
		$(PDFTOPPM_LIBS)

#------------------------------------------------------------------------

PDFTOPNG_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	SplashOutputDev.o \
	Stream.o \
	TextOutputDev.o \
	TextString.o \
	UnicodeMap.o \
	UnicodeTypeTable.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdftopng.o
PDFTOPNG_LIBS = -L$(GOOLIBDIR) -lGoo $(SPLASHLIBS) $(FTLIBS) \
	$(OTHERLIBS) $(PNGLIBS) -lm

pdftopng$(EXE): $(PDFTOPNG_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdftopng$(EXE) $(PDFTOPNG_OBJS) \
		$(PDFTOPNG_LIBS)

#------------------------------------------------------------------------

PDFIMAGES_OBJS = \
	AcroForm.o \
	Annot.o \
	Array.o \
	BuiltinFont.o \
	BuiltinFontTables.o \
	Catalog.o \
	CharCodeToUnicode.o \
	CMap.o \
	Decrypt.o \
	Dict.o \
	Error.o \
	FontEncodingTables.o \
	Form.o \
	Function.o \
	Gfx.o \
	GfxFont.o \
	GfxState.o \
	GlobalParams.o \
	ImageOutputDev.o \
	JArithmeticDecoder.o \
	JBIG2Stream.o \
	JPXStream.o \
	Lexer.o \
	Link.o \
	NameToCharCode.o \
	Object.o \
	OptionalContent.o \
	Outline.o \
	OutputDev.o \
	Page.o \
	Parser.o \
	PDFDoc.o \
	PDFDocEncoding.o \
	PSTokenizer.o \
	SecurityHandler.o \
	Stream.o \
	TextString.o \
	UnicodeMap.o \
	XFAForm.o \
	XpdfPluginAPI.o \
	XRef.o \
	Zoox.o \
	pdfimages.o
PDFIMAGES_LIBS = -L$(GOOLIBDIR) -lGoo $(OTHERLIBS) -lm

pdfimages$(EXE): $(PDFIMAGES_OBJS) $(GOOLIBDIR)/$(LIBPREFIX)Goo.a
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o pdfimages$(EXE) $(PDFIMAGES_OBJS) \
		$(PDFIMAGES_LIBS)

#------------------------------------------------------------------------

clean:
	rm -f $(XPDF_OBJS) xpdf$(EXE)
	rm -f $(PDFTOPS_OBJS) pdftops$(EXE)
	rm -f $(PDFTOTEXT_OBJS) pdftotext$(EXE)
	rm -f $(pdftoxml_OBJS) pdftoxml$(EXE)
	rm -f $(PDFINFO_OBJS) pdfinfo$(EXE)
	rm -f $(PDFFONTS_OBJS) pdffonts$(EXE)
	rm -f $(PDFDETACH_OBJS) pdfdetach$(EXE)
	rm -f $(PDFTOPPM_OBJS) pdftoppm$(EXE)
	rm -f $(PDFTOPNG_OBJS) pdftopng$(EXE)
	rm -f $(PDFIMAGES_OBJS) pdfimages$(EXE)

#------------------------------------------------------------------------

depend:
	$(CXX) $(CXXFLAGS) -MM $(CXX_SRC) >Makefile.dep

-include Makefile.dep
